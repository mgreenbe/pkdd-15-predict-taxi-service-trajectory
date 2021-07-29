# Exercise

This exercise is based on the Kaggle competition, **ECML/PKDD 15: Taxi Trajectory Prediction (I):
Predict the destination of taxi trips based on initial partial trajectories**.

From the [overview](https://www.kaggle.com/c/pkdd-15-predict-taxi-service-trajectory-i/overview):

> To improve the efficiency of electronic taxi dispatching systems it is important to be able to predict the final destination of a taxi while it is in service. Particularly during periods of high demand, there is often a taxi whose current ride will end near or exactly at a requested pick up location from a new rider. If a dispatcher knew approximately where their taxi drivers would be ending their current rides, they would be able to identify which taxi to assign to each pickup request.
> 
> The spatial trajectory of an occupied taxi could provide some hints as to where it is going. Similarly, given the taxi id, it might be possible to predict its final destination based on the regularity of pre-hired services. In a significant number of taxi rides (approximately 25%), the taxi has been called through the taxi call-center, and the passenger’s telephone id can be used to narrow the destination prediction based on historical ride data connected to their telephone id.
>
> In this challenge, we ask you to build a predictive framework that is able to infer the final destination of taxi rides in Porto, Portugal based on their (initial) partial trajectories. The output of such a framework must be the final trip's destination (WGS84 coordinates).

The dataset is a `csv` file, one of whose columns &mdash; `POLYLINE` &mdash; contains a initial partial trajectory strings of taxi trips, in the form of lists of pairs of longitude/latitude coordinates:
```
"[[-8.585676,41.148522],[-8.585712,41.148639],[-8.585685,41.148855],[-8.58573,41.148927],[-8.585982,41.148963],[-8.586396,41.148954],[-8.586072,41.14872],[-8.586324,41.147847],[-8.586999,41.14746],[-8.586576,41.147154],[-8.584884,41.146623]]"
```

## Your task

1. Load `test.csv` into a `pandas` dataframe; call it `df`.
2. Add columns `first_long`, `first_lat`, `last_long`, `last_lat`, with datatype `float`, containing the first and last reported positions for each trip.
3. Prepare a "baseline" submission file (see `sampleSubmission.csv` for the format) where the prediction fo a trip's final destination is, simply, it's last reported position.
4. Submit your submission file to Kaggle. Here's the [submission link](https://www.kaggle.com/c/pkdd-15-predict-taxi-service-trajectory-i/submit). Where, on the leader board, does this na&iuml;ve approach land you?
5. [extra credit] Add a column to `df` with the distance, in kilometers, of each partial trajectory.

