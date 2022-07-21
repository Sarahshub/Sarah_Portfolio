# Sarah_Portfolio
Data science portfolio of larger projects

## Project 1 Master Thesis: Offline Reinforcement Learning with Deep Kalman Filters.

**Abstract:** Offline reinforcement learning can introduce optimal policies for control problems in the world. However, uncertainty and risks are road blockers to the application of current models in critical settings. There is a need for system dynamics models that can handle non-linear environments and distribution shifts. The report addresses dynamics models through behavioral cloning of a collected target policy. A deep Kalman filter is constructed by assuming that the latent state space governs the system dynamics. Furthermore, the state transition distribution and the observation distribution are normal random variables. Therefore we can infer the latent state through bayesian filtering. A neural ordinary differential equation’s net is used to model the dynamics of the state transition parameters. To make the problem dynamic and non-linear, environments from Open AI gym are utilized. The performance of the deep Kalman filter and the baseline models is evaluated offline and online. Offline through the accuracy and the expected calibration error. Online the cumulative reward is observed. In the test, the deep Kalman filter yields a conservative accuracy score, the lowest expected calibration error, and the highest cumulative reward when deployed online. The model would benefit from further testing in different non-linear environments with increased dimensionality.

**Keywords:** Reinforcement learning, Offline reinforcement learning, Deep learning, Q-learning, State space models, Feedforward network, LSTM, Behavioral Cloning, Time series, Dynamic, Non-linear, Control tasks, Expected calibration error, Kalman filter. 

**Process:**<br>
In the project, a combined approach of reinforcement learning and offline reinforcement learning is used to solve for a target policy, collect data, train the environment dynamics models, and finally testing of the included models.
Q-learning solves for a target policy
The image above shows how Q-learning is used to solve for a target policy of the environment. Our agent consists of two policies; the one we try to learn and a greedy policy to ensure exploration and a learning function for updating our observed Q-values. The target policy is used to collect the data for behavioral cloning. For each time step per episode, a four tuple of (st, at, r, st+1) is collected. In the image below the models included for behavioral cloning are seen.

**Models:**<br>
A regular feedforward network and an LSTM model were included as baseline models for comparison. The models should map the right action to the given state from the environment. The feedforward network was fed random mini-batches with disregard for the sequence of the observations. The LSTM and Deep Kalman Filter were fed small sequences of different lengths to map the action to the state. The models were tested offline and online by deploying the trained models into the environments. The Deep Kalman Filter did display some properties which would be interesting to conduct further testing on.

