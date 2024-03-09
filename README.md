# KMCsequence
Kinetic Monte Carlo sequence evolution using a Potts Hamiltonian model

Step-by-step Instruction to eun the Kinetic evolution of sequence trajectories using a Potts energy function:
Step 1: Use "mcmcCPUgenThreaded.c" to generate a "cpu" file using "gcc -O3 mcmcCPUgenThreaded.c -lm -o cpu". This will generate a file named "cpu"
Step 2: Keep the Random123 file and cpu files in the current working directory.
Step 3: Run this code in Parallel by following: 
cat "input-sequence" | parallel './cpu "Potts-Hamiltonion file in .binary format" q n ABCD {} >output{#}'
where q = the interval steps by which you like to save your sequences and n= the total number of steps of the simulation.

Note: The Potts-Hamiltonian file refers to the J.npy file containing the Potts interaction parameters using Mi3-GPU in our case. Any other file containing the interaction parameters in the appropriate format is acceptable. For more details please follow the Mi3-GPU git repository at https://github.com/ahaldane/Mi3-GPU.  
