you can use `message = FALSE` to silence all the package startup messages

do you use all the packages you load? (I guess so ...)

saying "team as a random effect" is an insufficient specification - you mean that team is a RE *grouping variable*; you also need to specify what varies across these groups. The maximal model would almost certainly include random slopes, i.e. variation in effects of gdp and population across countries (any covariate that varies within groups can have its *across-group* variation included in the model)

what are "enough observations"? the problem with a single observation per level is not instability/overfitting, but actual confounding (jointly unidentifiable random effect and residual variances)

using observation-level random effects for Poisson models is in fact sensible -- this is one way of incorporating overdispersion (logNormal-Poisson models)

including year as a RE *grouping variable* may make sense when year is included as a *continuous* covariate in the fixed-effect model

Your 'maximal model' isn't (see comments above about random-slopes models)

What happens to country-year combinations with more than 5 gold medals? Not quite sure why gold medals are non-integer values???  (OK, you're plotting log(n+1) -- this should be in the y-axis label!)

Logging GDP (rather than scaling) would be a good way to make the plot clearer ... although faceting is a reasonable solution (note there are only 3 'medium GDP' and 1 'High GDP' countries - it would be worth identifying these ...

Gold medals vs population: please order your factors so that "low" comes before "high" ... !

You can adjust figure width/height to make check_model results prettier ...

Note that DHARMa (probably more reliable than check_model) *doesn't* think there is overdispersion ... although the dispersion parameter for the NB is relatively low, suggesting that it is actually doing something.

Note that the effects plots are useless unless they're on the log scale, or unless you truncated the CIs -- extrapolating the uncertainty to scaled GDP = 10

Q2  good choice of the model (it would be worth considering a random-slopes model ....)

when plotting smoothed outcome over time, you should probably either use quasibinomial or truncate y-axis at 0 ...

How did you decide on a probit link?

You should *never* make a coefficient plot that's not scaled, if the predictors have different units

I thought you said you were going to include a treatment-by-time interaction. What happened to it?

Better to establish a colour palette and use it rather than specifying each colour manually ...

Please supress the output from glmmPQL so your report doesn't have many pages of "iteration xxx"

It would be much better to find a way to plot all of the metrics together - the comparison *between* metrics is the most interesting piece. Having everything on separate plots makes it hard (and, bar plots require all results to be anchored at zero - not necessarily best for metrics that may have means far from zero)

mark: 8.5/10
