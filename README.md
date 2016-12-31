# quote-rate-trends
Predict time series trends on quote per invite rates in an online marketplace that matches freelance and business owners to consumers

# Problem:

A consumer posts a request for a service needed. Every request is in some category (e.g., Catering, Personal Training, Interior Design) and some location city. The company matches the request up with appropriate service providers and sends each of those providers an invite to quote on the request. Providers view the invite and some choose to send a quote to the consumer expressing interest.

We want to find answers to a critical long-term question for the business: Are service providers becoming more or less inclined to quote over time? 


# Quote rate trending

In order to do this, we measure the quote/invite rate and the proportion of invites that result in a quote as key metric for monitoring this.


# Data

Fictional dataset containing requests, invites and quotes over a two month period in response to the question of whether service providers are becoming more or less inclined to quote over time. SQLite database schema:

-categories 
-locations
-users holds the user ID and email for all users, both consumers and service providers
-requests has a row for each request posted by a consumer
    user_id references the consumer who posted the request
    category_id and location_id reference the categories and locations tables for the category and location of the request
    creation_time is when the consumer posted the request
-invites has a row for each invite sent to a service provider
    request_id references the request that this invite was sent for
    user_id references the service provider that this invite was sent to
    sent_time is when the invite was sent to the service provider
-quotes has a row for each quote a service provider sent in response to an invite
    invite_id references the invite that this quote was sent in response to
    sent_time is when the service provider sent the quote



# Analysis

See IPython notebook for full analysis on the QIR (Quote per Invite Rate). Note that it only shows the non interactive plots. To show the interactive plots and distribution and variability of each service, category and location where these are requested /invited for quoting/quoted, see:

https://plot.ly/~NataliaDiazRodr/7/most-common-service-request-categories-per-location/

https://plot.ly/~NataliaDiazRodr/11/number-of-service-requests-per-category/

https://plot.ly/~NataliaDiazRodr/9/number-of-service-requests-per-location/

https://plot.ly/~NataliaDiazRodr/11/qir-variability-over-time/

https://plot.ly/~NataliaDiazRodr/78/qir-variability-per-category/

https://plot.ly/~NataliaDiazRodr/64/quote-per-invite-ratio-per-category/




