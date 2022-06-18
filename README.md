# Kickstarter-analysis
Performing Analysis on Kickstarter Data to uncover trends
## Overview of the Project:
    The purpose of this analysis is to help an upcoming playwright Louise who wants to start a 
    crowdfunding campaingn to underplay fever. she is estimating a budget of $10,000.
## Analysis and Challenges
#### The first step in the analysis is to take an initial look at the data.
      * By intial look at the data provided:
          - we can learn how large the data we are working with.
          - To familiarize with the type of data present also Checking whether all the data type 
            is classified correctly.
          - Is the Data readable or does it need to convert. 
            **Observations**
            Column I & J look like data but are not readable 
            they contain unix timestamps rather than standard format.
#### The next step is to Organise the data.
      * lets understand the data in each column that we are working with:
        1. Goal Column tells how much money each campaign will need to succeed.
        2. Pledge Column tells how much money each campaign actually made.
        3. Outcome column tells whether campaign was successful or not.
        4.Country column tells us which country campaign was started.
        **Observations**
        - Many of the campaigns missed their goal amount by a small margin.
      * Percentage funded column helps to determine how much of the campaign goal was met.
        - Crowdfunding platforms, allows project creators to add incentives for different 
          pledge amounts. 
      * Average Donations Column helps us to determine how much money people have 
        pledged to campaigns. But this column has an error. ickstarter requires every campaign to have a fundraising goal. However, not every campaign has backers, which means, in some cases, there is no number to divide by in the formula.
      
