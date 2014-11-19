SGEcode
=======

Simultaneous Gaussian and Exponential Inversion for Improved Analysis of Shales by NMR Relaxometry

Code for the simultaneous Gaussian and exponential inversion of NMR T2 relaxometery data that may contain both Gaussian and exponential decays.  If you use this code, please cite the paper http://www.sciencedirect.com/science/article/pii/S109078071400295X  in any resultant publications.  

The code is written in the R programming language.  An example to execute the function is given below, though other optimisation methods should also work. 

SGE.fit<-optim(rep(0,length(T2.Values)*2),fn=SGE,M=Measured.Data,to=T2.axis,T2=T2.Values,
smoothing=0.001,sig=41,sigwidth=1.0,sigweightA=0.01, sigweightB=0.01,
lower=Max, upper=Min, control=list(maxit=20000000), method=“L-BFGS-B”)

M is the measured T2 relaxation data.  to is the time axis of the T2 relaxation data.  T2 is the range of T2 values over which the function is searching for a solution. sig is the center of the sigmoid function as an index of the vector of T2. The minimisation may time out after a certain number of iterations before convergence is reached.  This can be avoided by increasing the value of maxit.
