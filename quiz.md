# Interactive Plotting Quiz
This quiz is part of Algoritma Academy assessment process. Congratulations on completing the Interactive Plotting course! We will conduct an assessment quiz to test your ability in making interactive plot and dashboard that you have learned on the course. The quiz is expected to be taken in the classroom, please contact our team of instructors if you missed the chance to take it in class.

## Inspecting Dataset
 
We will be using a dataset of trending videos in YouTube stored in `youtube.csv`. The data consists of all trending videos in the United States from November 2017 to January 2018 with a total of 2986 observations and 9 variables. Please use the following glossary for reference:

 * `trending_date`: Video trending date
 * `title`: Video title
 * `channel_title`: Name of the YouTube channel
 * `category_id`: Video category
 * `publish_time`: Date when the video was published
 * `views`: Number of video views
 * `likes`: Number of video likes
 * `dislikes`: Number of video dislikes
 * `comment_count`: Number of video comments

Read the dataset and save it into an object named `youtube`:

```{r}
# Your code here
```

Say you are working as a trend analyst consultant for a YouTube channel. You are trying to capture the top rating YouTube channels listed under the **Music** category. The metrics you are using to rate each channel is the ratio between likes and views (likes ratio).

Take the top 10 YouTube channels based on the highest likes ratio by completing the code below:

```{r}
library(dplyr)
youtube %>% 
   ___(category_id == "Music") %>% 
   group_by(channel_title) %>% 
   ___(likes_ratio = mean(likes/views)) %>% 
   ___(desc(likes_ratio)) %>% 
   head(10)
```
___

1. Which `dplyr` functions is appropriate to fill in the code above?
  - [ ] filter, summarise, arrange
  - [ ] select, pivot, order
  - [ ] filter, mutate, order
  - [ ] select, summarise, arrange
___

## Building Dashboard Application

Based on the YouTube channels you have extracted, you are planning to create a dashboard prototype for your client using a flexdashboard. You created a mockup with the following design:

![](assets/mockup.png)
___
2. To produce the layout using flexdashboard templates, how should the layout be structured?
  - [ ] orientation: rows ; 2 headers in first section, 1 headers in the second section
  - [ ] orientation: columns ; 2 headers in first section, 1 headers in the second section
  - [ ] orientation: columns ; 1 headers in first section, 2 headers in the second section
  - [ ] orientation: rows ; 1 headers in first section, 2 headers in the second section
___

Now pay attention to the top-right plot. The plot shows the likes ratio and dislikes ratio across trending videos within the Music category. Say you would like to add a shiny interactivity feature where users could pick their desired category and the plot would change accordingly.
___
3. Which one from the input type below is appropriate for the given type of selection?
  - [ ] selectInput()
  - [ ] sliderInput()
  - [ ] numericInput()
  - [ ] passwordInput()
___
  
You would also like to have the top right plot to be able to show each video title for further analysis. Since you realized that creating a geom_text could be overcrowded for the plot, you are planning to render a plotly object that shows each video title for each hover action.
___
4. Which of the following code is correctly paired between render function and output in order to create the plotly object on Shiny Dashboard?
  - [ ] output$plot1 <- renderPlot({}) ; plotlyOutput("plot1")
  - [ ] output$plotly1 <- renderPlotly({}) ; plotOutput("plotly1")
  - [ ] output$plot1 <- renderPlot({}) ; plotOutput("plot1")
  - [ ] output$plot1 <- renderPlotly({}) ; plotlyOutput("plot1")
 ___
