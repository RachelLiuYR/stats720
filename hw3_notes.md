you'll get nicer output from check_model() if you set the figure height and width (set fig.height, fig.width in the chunk options, to something like 10 and 7) (you seem to have done this for the next plot, so why not this one?)

I wouldn't even bother checking collinearity ...

e) verbal description of comparison?

You never need `== TRUE` in R code; in this case it's a little weird, but you should use `isTRUE()` for `all.equal()`

ddf comparison: best to comment on the *practical* importance of these differences (==very small)

"does not provide a baseline estimate for the overall population-level effect of sex on attainment, so we cannot estimate an overall population level of sex on attainment"; this is a little misleading. The problem is that it sets the baseline estimate to zero (which is artificial/strange)

Definitely shouldn't compare AIC, log-likelihood in these ways; only *differences* in these metrics are important, and they can be evaluated on an *absolute* scale.

I'm curious what ChatGPT told you to do about addressing convergence failure (and how it differed from ?lme4::troubleshooting, ?lme4::convergence, or https://bbolker.github.io/mixedmodels-misc/glmmFAQ.html#convergence-warnings

mark: 9.5/10
