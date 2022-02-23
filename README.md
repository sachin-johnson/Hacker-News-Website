# Hacker News Website

[Hacker news](https://news.ycombinator.com/) is a website extremely popular in technology and startup circles. User submitted stories (known as "posts") are voted and commented upon by the site visitors. 

## Aim

The aim is to analyze Hacker news website, to find the most popular post category and the suitable time to submit the post, in order to receive greater comment engagement. As popular posts belong to `Ask HN` or `Show HN`, we will only consider these for further analysis.

* Users submit `Ask HN` posts to ask the Hacker News community a specific question.
* Users submit `Show HN` posts to show the Hacker News community a project, product, or just generally something interesting.

The following questions has to be answers before we arrive at a conclusion.

* Do `Ask HN` or `Show HN` posts receive more comments on average?
* Do posts created at a certain time receive more comments on average?

## Input dataset

Dataset used by this project can be downloaded [here](https://www.kaggle.com/hacker-news/hacker-news-posts). Below are descriptions of the columns present in the dataset.

* `id`: The unique identifier from Hacker News for the post.
* `title`: The title of the post.
* `url`: The URL that the post links to, if the post has a URL.
* `num_points`: The number of points the post acquired, calculated as the total number of upvotes minus the total number of downvotes.
* `num_comments`: The number of comments that were made on the post.
* `author`: The username of the person who submitted the post.
* `created_at`: The date and time at which the post was submitted.

## Data Cleaning

* Removing posts that received no comments.
* Filtering `Ask HN` and `Show HN` posts from the dataset.

## Data Analysis

We will try to answer the following during data analysis.

* Calculate the average number of comments received for Ask HN and Show HN posts, to find the popular post category. 
* Analyze the average number of comments received by post based on its hour of creation.

To determine if the posts created at a certain time are more likely to attract more comments. We'll use the following steps.

* Calculate the number of posts created in each hour of the day, along with the number of comments received by them.
* Calculate the average number of comments post receive based on the hour of its creation.

Note: According to the data set [documentation](https://www.kaggle.com/hacker-news/hacker-news-posts/home), the timezone used is Eastern Time in the US. We will need to convert it to Indian Standard Time(IST).

From analysis, we can infer that it is better to create a `Ask HN` post from 00:00 - 01:00, 01:00 - 02:00 or 22:00 - 23:00 respectively.

For `Show HN` post there isn't much difference between average comment value. Thus the time of post creation is not as critical for `Show HN` post as compared to `Ask HN` post. It's still better to create `Show HN` post between 23:00 and 24:00 IST.

## Conclusion

`Ask HN` posts are more popular by comments engagement with an average `Ask HN` post receiving 13.74 comments per post versus 9.81 comments per post for `Show HN`. Best hour for post creation based on average comments received is as follows.
* For `Ask HN` post: Between 00:00 - 01:00 (12 am - 1 am IST), with an average of 30.92 comments per post.
* For `Show HN` post: Between 23:00 - 24:00 (11 pm - 12 am IST), with an average of 12.24 comments per post.
    
Hacker news website is more widely used by Americans, the suitable time for post creation is presented in IST(Indian Standard Time) and this points to the late hours mentioned above. EST(Eastern Standard Time) in USA is about 09 hours 30 minutes behind IST. This corresponds to mid afternoon in USA.
