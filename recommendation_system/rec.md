# Overview
## The point of recommender system
* help people find information they are looking for
* get right content to the right people
## Information retrieval
* same result for same query
* invest effort in indexing content
## Information filtering
* same query, different results for different users
* invest in modeling user need: build user profile
## Collaborative filtering
* Automated CF *first recommender system was using this approach*
* Collaborative *using data from other users to do recommendation*
## Recommendation approaches
* Non-personalized and stereotyped
* Product association
* Content-based
* Collaborative
# Preferences and Ratings
## Explicit preferences
### Rating
* Star rating *Amazon*
* Up/down *Reddit, YouTube*
* Like *Facebook*
### Review
### Vote
## Implicit preferences
### Click
### Purchase
### Follow
# Predictions and Recommendations
## Predictions
quantified estimates of how much a user will like an item
### pro
helps quantify item
### con
falsifiable
## Recommendations
suggestions for items a user might like
### pro
provide choices
### con
poor recommendations lead to failure to explore
# Recommenders
## analytical framework
* domain
* purpose
* recommendation context
* whose opinions
* personalization level
* privacy and trustworthiness
* interfaces
* recommendation algorithms
### domains of recommendation
* news, information, 'text'
* products, vendors, bundles
* matchmaking *other people*
* sequences *music playlist*   
an interest perspective
* new items *movies, books*
* re-recommend old ones *groceries, music*
### purposes of recommendation
* the recommendations themselves
 * sales
 * information
* education of user/customer
* build a community of users/customers around products or content *TripAdviser*
### recommendation context
* what is the user doing at the time of recommendation?
 * shopping
 * listening to music
 * hanging out with other people
* how does the context constrain the recommender
### whose opinion?
* experts *wine.com*
* folks
* people like you
### personalization level
* generic/non-personalized: everyone receives same recommendations
* demographic: matches a target group
* ephemeral: matches current activity
* persistent: matches long-term interests
### privacy and trustworthiness
### interfaces
* types of output
 * predictions
 * recommendations
 * filtering
 * organic vs. explicit presentation
* types of input
 * explicit
 * implicit
### recommendation algorithms
* non-personalized summary statistics
* content-based filtering
 * information filtering
 * knowledge-based
* collaborative filtering
 * user-user
 * item-item
 * dimensionality reduction
* others
 * critique/interview based recommendations
 * hybrid techniques
### non-personalized summary stats
* external community data *best-seller; most popular; trending hot*
* summary of community ratings *best-liked*
### content-based filtering
break items down to attributes, each attribute has a value, an item can be represented by a vector of attributes (values), calculate distance between query item and the rest items, then rank
### collaborative filtering
### evaluation
