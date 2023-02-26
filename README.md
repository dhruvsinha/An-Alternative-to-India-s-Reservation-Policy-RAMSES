# An Alternative to India's Reservation Policy-RAMSES

## Abstract 

Affirmative action in the form of reservations is a divisive
and contentious topic of policy in India. In this paper, we
create the first principled and data-driven model to design the
reservations policy in India. We look at various issues that
critics present against the current reservation policy and try
resolve them, while pursuing a (provably) more effective and
efficient system of empowerment. We use intelligent statistical
modelling to create our new framework, RAMSES (Rigorous
and Adaptive Measurement of Socio-Economic Status). RAMSES measures the multidimensional disadvantage faced by an
individual as an “adjusted income”. This adjusted income calibrates the quantum of compensatory aid required in the form
of reservations for that individual to have a level playing field.
A flexible and dynamically adaptive framework like RAMSES
will empower policymakers, reduce bias, and become more
broadly accepted in society as a foundation on which rational
negotiations for reservations can happen, instead of the politically charged (and often violent) altercations that currently
drive these processes.

**This paper was published in the [ACM 2020 COMPASS Connference](https://dl.acm.org/doi/abs/10.1145/3378393.3402240)**

**If you want access to the code or the dataset, please email at dhruvsinha.09@gmail.com**

## Motivation

We see that the current system of reservation has its own set
of issues which policy makers and politicians have tried to
address in different ways. The current reservation system
provides and cares for group identities leading to the elite
among the group to become the biggest beneficiaries. The
provision to exclude the ‘creamy layer’ helps in keeping the
economically elite OBCs out of the reservation system. The
‘creamy layer’ however does not take into consideration that
there are other factors at play too which create an elite among
a certain group. Should we not prioritise women over men
when providing for reservation benefits if we see that men are
better off on all parameters as compared to women? If yes,
how will this prioritisation work? Scheduled castes from one
state might be facing a lot more discrimination as compared to
some other state. Should we not give more reservation benefits
to the more backward scheduled caste?

With so many complexities involved, it is not ideal to have a
homogeneous reservation policy across the length and breadth
of this country. Today, we have access to several datasets
and econometric tools which can let us deal with fairness (or
unfairness) of reservation policy at the level of the individual.
To motivate discussion for the need of a quantitative framework, we plot some important distributions. We compare top
10% of Scheduled Castes and OBCs (income wise) with bottom 10% of Forward Castes (including Brahmins). We first
plot the the distribution of number of Assets owned by each
Household. We can see in Fig 1 that distribution for Scheduled Castes and
OBCs is to the right of that Forward Castes.

| ![assests.jpg](/ramses-images/assets.jpg) | 
|:--:| 
||

We also plot the distribution of maximum education received
by any member of the Household. In Fig below, we see that the well to do Scheduled Caste
Households have almost the same distribution as impoverished Forward Caste Households. Moreover, well to do OBC
households have more educated household members. 

| ![education.jpg](/ramses-images/education.jpg) | 
|:--:| 
||

Similarly, we see that the
hourly wage distribution of rural Brahmins is the same as
that of rural Scheduled Castes. It can be seen from the flat
distribution that urban Brahmins have a much higher income
than rural and urban SCs.


| ![education.jpg](/ramses-images/rural_urban.jpg) | 
|:--:| 
||

It is because of these reasons, that we believe that a discussion on dynamic affirmative policy is needed. 

## Model

### Mincer Earning’s equation

In this method, we start by observing the parental income
of the individual. We hypothesize that parent’s income is probably the most important factor in determining the quality and
years of education that a child will receive. Income in the labor
market may depend upon several factors other than education
and skill. There can be 'taste for discrimination' in the labor
market against certain castes and females. Therefore, according to our Mincer Earning’s equation [15], the wage a parent or
household receives is a function of factors like Caste, sex, age,
education and residence. In our model, we calculate the impact
of each parameter and accordingly adjust the income to derive
adjusted income. As a result, the student is compensated for
the disadvantage his/her parents face in the labor market. To
calculate the adjusted income using this method, we use the
individual data of Indian Human Development Survey (IHDS),
2011. The IHDS is a nationally representative, multi-topic
survey of 41,554 households (2,00,000) individuals in 1503
villages and 971 urban neighborhoods across India. Our
estimation equation will look like this

$$log(hourly\_wage)= \beta_0+ \beta_1*Caste+\beta_2*urban+\beta_3*Male+\beta_4*educ+\beta_5*age+\beta_6*age^2+district FE+\mu$$
