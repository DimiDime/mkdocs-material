# Class for drone environment
  Drones_Env(gym.Env)
  Gym environment for controlling drones.
    The goal of this environment is to control a drone to reach a target position while avoiding obstacles.
    Observation:
        - weight_pos_obj (array): Weighted position difference between the drone and the target.
        - weight_pos_start (array): Weighted position difference between the drone and the initial position.
        - weight_vel_obj (array): Weighted velocity difference between the drone and the target.
        - weight_vel_start (array): Weighted velocity difference between the drone and the initial position.
        - weight_ang (array): Sine of the difference between the drone's orientation and the initial orientation.
        - weight_w (array): Weighted angular velocity difference between the drone and the initial angular velocity.
    Action:
        - pvx0 (float): Desired velocity in the x-direction.
        - pa0 (float): Desired angular velocity.
        - pp0 (float): Desired power.
    Reward:
        The reward is based on the distance to the target and the drone's velocity. Higher rewards are given for
        reaching the target with lower velocity.
    Done:
        The episode is considered done when the drone reaches the target or exceeds the maximum number of allowed
        actions.

## def __init__(self)
        Initializes the DroneEnv class.

        The method sets up the observation space and action space for the drone environment.

        Parameters:
        None

        Returns:
        None

## def reset(self, theta=None)
        Reset the environment to its initial state.

        Args:
            theta (float, optional): Angle of the target position. If not provided, a random angle is chosen.
        Returns:
            np.ndarray: The initial state of the environment.

## check_done(self):
        Check if the episode is done.
        Returns:
            bool: True if the episode is done, False otherwise.

    def step(self, action):
        """
        Take a step in the environment.
        Args:
            action (np.ndarray): The action to take.
        Returns:
            tuple: A tuple containing the next state, the reward, a flag indicating if the episode is done, and
            additional information.

# Heloer functions:

## plot_cylinder(ax, x, y, z, radius, height, num_points=25, alpha=0.8, color="blue"):
    Plot a cylinder on the given axes.
    Parameters:
    - ax: Axes object to plot on
    - x: x-coordinate of the cylinder center
    - y: y-coordinate of the cylinder center
    - z: z-coordinate of the cylinder base
    - radius: radius of the cylinder
    - height: height of the cylinder
    - num_points: number of points to use for the cylinder surface (default: 25)
    - alpha: transparency of the cylinder (default: 0.8)
    - color: color of the cylinder (default: 'blue')

## equation(pvy0, pa0, pp0):

    Calculate the time at which a drone reaches a certain position.
    Parameters:
    pvy0 (float): Initial vertical velocity of the drone.
    pa0 (float): Initial vertical acceleration of the drone.
    pp0 (float): Position of the drone at time t=0.

    Returns:
    tuple: A tuple containing the two possible times at which the drone reaches the given position.

## ham(state, tsa, tsb, tsc, end=1):
    Calculates the hamiltonian value for a given state and time parameters.
    Parameters:
    state (numpy.ndarray): The state vector.
    tsa (float): Time parameter a.
    tsb (float): Time parameter b.
    tsc (float): Time parameter c.
    end (int, optional): End value. Defaults to 1.
    Returns:
    float: The calculated hamiltonian value.

## shoot(costate, sf):
    Shoots the drone towards a target state.
    Parameters:
    costate (numpy.ndarray): The costate vector.
    sf (list): The target state.
    Returns:
    float: The norm of the difference between the target state and the final state of the drone.
