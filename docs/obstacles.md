This Python script uses reinforcement learning to simulate a drone navigating through an environment with obstacles. It employs the Proximal Policy Optimization algorithm (PPO) from Stable Baselines3. The drone adjusts its path based on obstacles, and the script visualizes the trajectory, obstacles, and final position. The simulation results, including scores and velocity components, are plotted.

## def m_calc(x0, y0):
    Calculate the values of m1 and m2.

    Parameters:
    x0 (float): The x-coordinate.
    y0 (float): The y-coordinate.

    Returns:
    tuple: A tuple containing the values of m1 and m2.

## compute_direction(p1, p2):
    Compute the direction from point p1 to point p2.

    Parameters:
    p1 (tuple): The coordinates of point p1 in the form (x1, y1).
    p2 (tuple): The coordinates of point p2 in the form (x2, y2).

    Returns:
    float: The direction in radians from p1 to p2.
