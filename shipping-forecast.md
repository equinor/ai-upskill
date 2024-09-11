# Shipping Forecast

A machine learning challenge aimed at data scientists, developers, and other technical people. It can be run as a slow-motion data science contest, or a short hackathon, or a combination of these.


## Task

Given a set of features about various items, including quantity, origin postcode, destination postcode, and shipping date, teams must predict the shipping time, which ranges from 0 (same day) to 21 days or more. The task can be treated as a classification or a regression. The features include both continuous and categorical variables, and some feature engineering or encoding is recommended. 


## Dataset

The following features are present:

- `IDX` &mdash; Record index.
- `MATNR_TEXT` &mdash; Material text description
- `NORSOK` &mdash; [NORSOK-M](https://standard.no/en/sectors/petroleum/norsok-standards/m-material/) material categorty
- `MENGE` &mdash; Item count
- `LIFNR_NAME` &mdash; Vendor name
- `LIFNR_ZIPCODE` &mdash; Vendor postcode
- `LIFNR_MUNI` &mdash; Vendor municipality
- `LIFNR_COUNTY` &mdash; Vendor county
- `WERKS_ZIPCODE` &mdash; Plant postcode
- `WERKS_MUNI` &mdash; Plant municipality
- `WERKS_COUNTY` &mdash; Plant county
- `DIST_KM` &mdash; Driving distance in km, provided by Google Maps API
- `PICKUP_DATE` &mdash; Pickup date and time

The final column in the CSV is the target property: the time to ship.

- `DEL_TIME` &mdash; Integer number of days; contains NULL for the test records


## Evaluation

A small Python FastAPI application facilitates the scoring of entries and provides a simple leaderboard. Teams interact with the API either via the Swagger docs, or in code using Python `requests` or similar. There is no Python API for taling to the web app, but this might be a cool idea.

It currently lives in [a private repo](https://github.com/scienxlab/adjudicator).

### The evaluation dataset

The test set was sampled randomly from the original dataset. There are 4533 records in the test set; they are the last rows in the CSV and they do not have a `DEL_TIME` value.

### The evaluation metric

The project owner wishes to measure the model's accuracy with the overall **precision** of the prediction. In other words, the proportion of correct predictions to the total number of predictions. You can compute this directly with `sum(y_true==y_pred) / y_true.size` or with Scikit-Learn:

```python
from sklearn.metrics import precision_score

# Assumes all values compare equal to integers.
precision_score(y_true, y_pred, average='micro')
```


## Formats

### Mini-hackathon

We ran this event in August 2024 as a short 'hackathon' with about eight teams of four. Each team drew a random constraint which limited their choice of learning algorithms:

- **Linear methods only**, not including trees or nonlinear kernels.
- **Tree methods only**, including groups of trees.
- **Neural networks only**, including any architecture.
- **Wildcard**, including whatever you like.

The teams had 2 hours, split into the following chunks:

- The first team to submit an entry won a small prize (a cookie). Next time, I would give cookies to each team upon making their first entry. This should fill up the leaderboard with early attempts.
- At 60 minutes, we had an 'intermediate sprint', with the top 3 teams receiving a small prize (some stickers and some candy). At this point we also **changed the scoring metric**.
- At 120 minutes, we had the final scores, with the top 3 teams receiving a prize (Lego trophies, water bottles, and chocolate respectively). 

Changing the scoring metric should be carefully considered. If you start with a loss, continue with a loss; if you start with a score, then keep it as a score. Also, make sure the metric actually works as advertised (ha!). In our event, no-one was able to beat the dummy model of predictig the average, which was amusing and a lesson in itself, but not the intended outcome! 

When we run it again we will stick to one scoring metric, and allow teams more time. (Also, I hosted the scoring app on my laptop, but a couple of people were not able to connect to my IP address. Next time I will find a proper server to host it on.)

### Other formats

You could also run the contest asynchronously. I think it's hard enough to do well that the contest could last at least a couple of weeks.
