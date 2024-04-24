## Bakery Selection and Operation Simulation

In a small town, there are five bakeries competing for customers' bread purchases. As economists, our task is to model how consumers might choose between these bakeries using a beta distributed probability model. This model allows us to explore how each success (utility with a value of 0 or 1) from a bakery influences the consumer's choice for the next day and beyond. 

### Modeled Beta Distribution & Assumption

In the bakery selection and operation simulation project, we make the following assumptions regarding the probability distribution of success for each bakery:

- **Assumptions**:
    - The probability of success for each bakery follows a Beta distribution.
    - Each bakery generates a utility with the value 1 or 0
    - The consumer needs bread everyday and constantly has the problem to choose between 5 bakeries
- **Formula**:

`Beta(ones + 1, zeros + 1)`
- **Description**: 
    - The Beta distribution is a continuous probability distribution defined on the interval [0, 1], making it suitable for modeling probabilities.
    - In our simulation, we use the Beta distribution to model the probability of success for each bakery.
    - The parameters of the Beta distribution are determined by the number of successes (`ones`) and failures (`zeros`) observed for each bakery.
    - By adding 1 to both successes and failures, we incorporate a form of Bayesian smoothing, preventing probabilities of 0 or 1 and allowing for some uncertainty in the estimation of success probabilities.
    - This formulation ensures that the probability of success for each bakery is updated dynamically based on its past performance, allowing for adaptive decision-making in bakery selection.
 

### Simulation Overview

1. **Initialization**: 
    - Five bakeries are defined, each initially assigned an equal probability of success.
    - Information about each bakery, including success and failure counts, is stored in a DataFrame called 'df'.

2. **Bakery Selection**:
    - For each day of each month:
        - A bakery is selected for operation based on its probability of success, with the bakery having the highest probability being chosen.
        - Initially, on the first day of the month, a bakery is randomly selected. Subsequent days select the bakery with the highest probability of success.

3. **Operation Simulation**:
    - The selected bakery's operation is simulated, resulting in either success or failure based on its probability.

4. **Result Updating**:
    - The simulation updates each bakery's success and failure counts based on the outcome of its operation.
    - The probability of success for each bakery is adjusted using a Beta distribution.

5. **Data Collection and Visualization**:
    - Information about each day's operation is collected and stored in a DataFrame called 'df1'.
    - The Success Rate of each bakery over the months is visualized to understand the simulation outcomes.

### Conclusion

The one-year simulation of bakery operations offers valuable insights into consumer behavior and bakery performance:

1. **Bakery Selection Process**: 
    - Bakery4 emerges as the most frequently selected bakery, boasting a significant number of successes (192) compared to relatively fewer failures (77), resulting in a commendable success rate of approximately 0.678. This suggests that Bakery4 consistently met or exceeded customer expectations, making it a preferred choice.
    - Bakery1 also performs well, maintaining a balanced ratio of successes (39) to failures (30), resulting in a success rate of around 0.443. While not as dominant as Bakery4, Bakery1 demonstrates promising performance.
    - Bakery2, Bakery3, and Bakery5 exhibit lower success rates, indicating areas for improvement to enhance their appeal to consumers.

2. **Implications**:
    - Bakery4 emerges as the most reliable option for consistent success in bakery operations, suggesting that maintaining quality and meeting customer expectations are crucial factors for bakery success.
    - Bakeries with lower success rates may need to analyze and optimize their operations to improve efficiency and enhance their success rates, thereby increasing their competitiveness in the market.

In summary, this simulation demonstrates the effectiveness of using a beta distribution model to understand consumer behavior and its relationship with bakery quality. By analyzing bakery selection patterns and performance, stakeholders can make informed decisions to optimize bakery operations and improve market competitiveness.
