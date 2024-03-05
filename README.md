# Conjugate_Gradients_2024_EUMaster4HPC_Challenge

# Conjugate gradient method

## Steps for running the code on MeluXina

```
salloc -A p200301 --res cpudev -q dev -N 1 -t 00:30:00
```

```
module load intel
```

```
mkdir io
```

```
icpx -O2 src/conjugate_gradients.cpp -o conjugate_gradients -fopenmp
```

```
export OMP_PROC_BIND=true
```

To generate a random SPD system of 10000 equations and unknowns and to then solve the system

```
./random_spd_system.sh 10000 io/matrix.bin io/rhs.bin
```

```
./conjugate_gradients io/matrix.bin io/rhs.bin io/sol.bin
```
