This Python script utilizes numpy, TensorFlow, and scipy to model drone dynamics. It defines physical constants, drone parameters, and axis length. The code includes functions for calculating derivatives in drone dynamics (`f`), computing control inputs based on the state (`controls`), and a function for a linear system (`f_linear`). The simulation loop commented out for now, generates random initial conditions to simulate the drone's behaviour and plots various aspects of the simulation. The script focuses on numerical integration, providing a concise representation of drone dynamics under different conditions.

## f(t, state):
    Calculate the derivative of the state vector for the drone dynamics.

    Parameters:
    t (float): Time.
    state (list): List containing the state variables [x, y, z, vx, vy, vz, a, b, c, p, q, r, T].

    Returns:
    numpy.ndarray: Derivative of the state vector.

## controls(state):
    Calculates the control inputs for the drone based on the current state.

    Parameters:
    state (array-like): Array containing the current state of the drone. The state should have the following elements:
                        x, y, z, vx, vy, vz, a, b, c, p, q, r, px, py, pz, pvx, pvy, pvz, pa, pb, pc, pp, pq, pr, Time
    Returns:
    array-like: Array containing the control inputs for the drone. The control inputs are in the following order:
                T0, Ma, Mb, Mc

## f_linear(t, state, tsa, tsb, tf, obj):
    Calculates the derivative of the state vector for a linear system.
    Args:
        t (float): Current time.
        state (numpy.ndarray): State vector containing the current values of the system variables.
        tsa (list): List of two time points representing the start and end of a time interval.
        tsb (list): List of two time points representing the start and end of another time interval.
        tf (float): Final time.
        obj (numpy.ndarray): Object coordinates.
    Returns:
        numpy.ndarray: Derivative of the state vector.
    
