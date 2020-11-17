#### MATLAB-Generation-of-Normal-Random-Number-Variables-and-T-tests

##### REQUIREMENTS
    Matlab r2018a to r2020a
 
 ######  Installation cracked version  
 https://www.pirate-bay.net/search?q=Spss#
 
> Instructions

Need to be keen while loading MATLAB files (the one with. mlx extension) in the MATLAB program: -

#### Setting up rng (random number generator) 
  Sometimes errors may pop after loading the files which may hinder the entire program from running as usual.
  
•	It may be caused by changing the name of the file or location of the file or minimal memory

•	How to solve this problem – create a new live script file, save it in your local computer,
then put the STUDENTID as follows rng(123456789), run the section by pressing F5,copy paste into the file, and save.

•	The program contains heavy data. You need to be patient and avoid unnecessary interruptions. 

###	NB: THE FILE MAY TAKE A WHILE; PLEASE ENSURE YOU ARE RUNNING ON HIGHER PROCESSING COMPUTER AND ALL OTHER PROGRAMS ARE CLOSED TO GIVE SPACE FOR THE FILE TO LOAD AND OUPUT DATA CORRECTLY AND FASTER
rng(470021907)

(i) Generate 9 mutually independent normally distributed random variables, X1,  . . , X9, where the ith of these random variables has expected value μ equal to             zero, and variance a2i
 %equal to the ith digit of your Student ID number. Collect these random variables into a 9 × 1 random vector, which we will view as a sample.

 %USE THE FOLLOWING SYNTAX TO GENERATE A RANDOM INTEGER
 %Y = randn(m,n) but we need to normalize to integer
 %NORMALLY DISTRIBUTED RANDOM VARIABLES
 %SUBDIVIDING BELOW ITERATIONS

    %Combined iteration
    for i=3:10000
    Yall = randn(9,1)
    end

    %splitted iteration
    for i=1:10
    if i>1 && i<10
    Y1 = randn(9,1)
    end
     i=i+1;
    end


    for i=10:100
     if i>10 && i<100
    Y2 = randn(9,1)
    end
     i=i+1;
    end

    for i=100:1000
     if i>100 && i<1000
    Y3 = randn(9,1)
     end
     i=i+1;
    end


    for i=1000:10000
     if i>1000 && i<10000
     Y4 = randn(9,1)
     end
    end


% Creating and Collecting 9x1 MATRIX random

    %unNORMALIZED OUTPUT DATA
    Y = randn(9,1)
    [barheights, positions]=hist(Y,10);

    dx=positions(2)-positions(1);


    bar(positions, barheights/(dx));
    [barheights, positions]=hist(Y1,10);

    dx=positions(2)-positions(1);

    bar(positions, barheights/(dx));
    [barheights, positions]=hist(Y2,10);

    dx=positions(2)-positions(1);

    bar(positions, barheights/(dx));
    [barheights, positions]=hist(Y3,10);

    dx=positions(2)-positions(1);

    bar(positions, barheights/(dx));
    [barheights, positions]=hist(Y4,10);

    dx=positions(2)-positions(1);

    bar(positions, barheights/(dx));

    %Normalization between 0 and 9
    number2int = uint64(9*mat2gray(Y)); 

    %Normalized version
    disp(number2int)


% (ii) Compute the t-statistic for testing the null hypothesis H0 : μ = 0.
%t-statistic for testing the null hypothesis H0 : μ = 0

%After a successfull 10000 monte carlo iteration

        h = ttest(Yall)
        [h,p]=ttest(Yall)


%(iii) Record whether the absolute value of the t-statistic exceeds cn−1 (α).

%NB:since the values are generated randomly the test results may differ

%My first test was successfull
 
%ANSWER:
% Tested on one epoch or one MC repetition
%One tailed hypothesis
    %Absolute value; cn−1 (0.05)=1-0.9878=0.0122
    %0.0122<0.05 
%Conlusion: IT does NOT EXCEED 

%ANSWER:
% Tested on 10000 MC repetition
    
    %One tailed hypothesis
    %Absolute value; cn−1 (0.05)=1-0.9878=0.0122
    %0.0122<0.05 
%Conlusion: IT does NOT EXCEED 


% Compute the proportion of Monte Carlo repetitions in which the absolute value of the푡-statistic exceeded푐푛−1(훼). Call this proportion rej(a)

    [h,p]=ttest(Y1)% monte carlo computation upto 10 repettiions
    [h,p]=ttest(Y2)% monte carlo computation upto 100 repettiions
    [h,p]=ttest(Y3)% monte carlo computation upto 1000 repettiions
    [h,p]=ttest(Y4)% monte carlo computation upto 10000 repettiions

%ANSWER

%At Y2 WHEN THE MONTE CARLO REPETITION IS 100 REP =rej(a) when p=0.9537

    %P=0.9537

%PART_2 OF QUESTION 2
% b) Th�e quantity rej(훼)computed in part (a) was constructed from randomlydrawn samples,
%so it is itself random. In fact, it is the average of 10,000 inde-pendent draws from the Bernoulli(푝)distribution, with푝equal to the prob-ability that the absolute value of the푡-statistic exceeds푐푛−1(훼)in absolutevalue.
% Using the normal approximation to the binomial distribution, test thehypothesis that푝=훼. Can you reject this hypothesis at the 5% signi�cancelevel?
% What about the 1% signi�cance level?

%SOLUTION

    %rej(a)0.05= when is at 1-0.9537=0.0463
    %AT 0.01 =0.5675




