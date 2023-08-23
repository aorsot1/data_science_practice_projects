# British Airways Reviews - Annotated Data Dictionary

## Introduction

British Airways, one of the world's leading airlines, has been synonymous with excellence and reliability for decades. With a rich history and a commitment to providing exceptional customer experiences, British Airways continues to be a preferred choice for travelers worldwide.

As part of a challenging and rewarding data science project at British Airways, I had the opportunity to work on web scraping review data from the renowned Skytrax website. The goal was to collect valuable insights from customer reviews and leverage data-driven approaches to enhance the airline's services and customer satisfaction.

## Variables
The dataset comprises the following columns, each providing essential information extracted from the reviews:

1. **reviews**: This column contains the text-based feedback and reviews provided by customers after their experience with British Airways.
    * Type: Text
    * Format: Verfied & Unverified
    
2. **sate**: The date on which the review was posted by the customer, offering valuable temporal information.
    * Type: Datetime
    * Format: Ranging from 11/10/2015 to 8/1/2023
    
3. **country**: Indicates the country of origin of the customer, allowing for regional analysis and understanding customer preferences.
    * Type: Text - Categorical
    * Format: 67 Distinct country names
    
4. **seat_type**: Provides insights into the type of seat the traveler experienced during their flight, including economy, premium economy, business, or first class. 
    * Type: Numerical - Ordinal Categorical
    * Format: Encoded with a given significant order as followed
        * 'Economy Class': 0
        * 'Premium Economy': 1
        * 'Business Class': 2
        * 'First Class': 3
        
5. **recommended_0**: A binary indicator for the travelers saying 'no' to recommending British Airways based on their experience.
    * Type: Numerical - Binary Categorical
    * Format: Encoded from a previous column called 'Recommended' with a binary encoder
    
6. **recommended_1**: A binary indicator for the travelers saying 'yes' to recommending British Airways based on their experience.
    * Type: Numerical - Binary Categorical
    * Format: Encoded from a previous column called 'Recommended' with a binary encoder
    
7. **stars**: The rating given by the traveler, typically on a scale of 1 to 10 stars, reflecting their overall satisfaction with the airline's services. 
    * Type: Numerical - Ordinal Categorical
    * Format: Encoded with a given significant order as followed
        * 1 : 0
        * 3 : 1
        * 5 : 2
        * 7 : 3
        * 9 : 4

8. **route**: This column provides information about the specific route or flight taken by the passengers, offering context to their reviews and
    * Type: Text - Categorical
    * Format: 10 Distinct routes with 12 distinct airports 
    
4. **Type of Traveler**: This column categorizes the type of traveler who left the review, distinguishing between different travel demographics, such as business travelers, families, or solo adventurers.
9. **type_of_traveller_Family Leisure**: A binary indicator for the families traveling for leisure
    * Type: Numerical - Cardinal Categorical
    * Format: Encoded from a previous column called 'Type of Traveler' with a One-Hot encoder
    
10. **type_of_traveller_Solo Leisure**: A binary indicator for the individual traveling for leisure
    * Type: Numerical - Cardinal Categorical
    * Format: Encoded from a previous column called 'Type of Traveler' with a One-Hot encoder
    
11. **type_of_traveller_Couple Leisure**: A binary indicator for the couples traveling for leisure
    * Type: Numerical - Cardinal Categorical
    * Format: Encoded from a previous column called 'Type of Traveler' with a One-Hot encoder

12. **type_of_traveller_Business**: A binary indicator for the anyone traveling for business
    * Type: Numerical - Cardinal Categorical
    * Format: Encoded from a previous column called 'Type of Traveler' with a One-Hot encoder
    
13. **trip_verified_0**: A binary indicator for reviews from "verified" travelers
    * Type: Numerical - Binary Categorical
    * Format: Encoded from a deleted column called 'trip_verified' (extracted from 'Reviews') with a binary encoder
    
14. **trip_verified_1**: A binary indicator for reviews from "unverified" travelers
    * Type: Numerical - Binary Categorical
    * Format: Encoded from a deleted column called 'trip_verified' (extracted from 'Reviews') with a binary encoder
    
14. **reviews_verif_drop**: Main content/message of each review
    * Type: Text
    * Format: Obtain actual written text by removing the leading term "✅ Trip Verified" and whitespace from 'reviews'
    
15. **reviews_bag_of_words**: List of words
    * Type: List
    * Format: Create a bag of words for further textual analysis if desired from 'reviews_verif_drop'
    
16. **country_encoded**: Numerical transformed 'country' column
    * Type: Numerical - Frequency Categorical
    * Format: Encoded from 'country' with a frequency encoder
    
17. **from**: Departure Airport
    * Type: Text - Categorical
    * Format: Extracted from 'country' and standardize to obtain airport code for each
    
18. **tol**: Arrival Airport
    * Type: Text - Categorical
    * Format: Extracted from 'country' and standardize to obtain airport code for each
