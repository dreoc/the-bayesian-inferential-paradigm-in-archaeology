---
title: "**The Bayesian Inferential Paradigm in Archaeology**"
author: 
  - ERIK OTÁROLA-CASTILLO*, MELISSA G. TORQUATO
  - Department of Anthropology, Purdue University, West Lafayette, Indiana, USA
  - CAITLIN E. BUCK
  - School of Mathematics and Statistics, University of Sheffield, Sheffield, UK
date: "*R Markdown version last compiled on Monday September 20 2021, 21:24:04, UTC*"
indent: yes
header-includes:
    - \usepackage{setspace}\doublespacing
    - \usepackage[labelfont=bf,width=1\textwidth,justification=raggedright,singlelinecheck=false]{caption}
    - \captionsetup[figure]{labelfont=bf}
    - \usepackage[pagewise]{lineno}
output: 
  pdf_document: 
    latex_engine: xelatex
    keep_md: false
  word_document: default
  html_document: default
link-citations: yes
bibliography: cite.bib
---




\vspace{4cm}
\noindent
**Manuscript accepted to the Handbook of Archaeological Sciences, 2nd ed. Forthcoming volume under contract. *Edited by* M. Pollard, R.A. Armitage, and C.M. Makarewicz. Willey.** 

\vspace{2.5cm}
\textbf{*\*Corresponding Author}
\noindent
email:\href{mailto:eoc@purdue.edu}{\color{blue} \,eoc@purdue.edu}\newline


\newpage







## INTRODUCTION
Archaeologists often use data and quantitative statistical methods to evaluate their ideas. Although there are various statistical frameworks for decision-making in archaeology and science in general, in this chapter, we provide a simple explanation of Bayesian statistics. To contextualize the Bayesian statistical framework, we briefly compare it to the more widespread null hypothesis significance testing (NHST) approach. We also provide a simple example to illustrate how archaeologists use data and the Bayesian framework to compare hypotheses and evaluate their uncertainty. We then review how archaeologists have applied Bayesian statistics to solve research problems related to radiocarbon dating and chronology, lithic, ceramic, zooarchaeological, bioarchaeological, and spatial analyses. Because recent work has reviewed Bayesian applications in archaeology from the 1990s up to 2017 [@buck_bayesian_1996; @buck_applications_2001; @otarola-castillo_bayesian_2018], this work considers the relevant literature published since 2017.

### Null hypothesis significance testing

Archaeologists use NHST to assess the extent to which well-observed material culture recovered from archaeological sites aligns with their hypotheses about past people. Statisticians pioneered the NHST inferential structure in the early twentieth century and, thanks to its success in research practice, it became widely available to scientists of the time [e.g., @fisher_statistical_1925; @neyman_problem_1933: 294]. In the 1950s, various science-oriented archaeological works introduced NHST methodology to the field [e.g., @myers_applications_1950; @spaulding_statistical_1953; @binford_consideration_1964; @clarke_analytical_1968]. Today, numerous textbooks continue to teach archaeological scientists introductory NHST statistical concepts such as confidence intervals and p-values [e.g., @fletcher_digging_2005; @carlson_quantitative_2017; @mccall_strategies_2018; @banning_archaeologists_2020]. 

Statistical methods that follow the NHST framework provide inference by estimating the parameters of a probability model used to represent the salient features of a population (e.g., the mean and variance). Scientists usually hypothesize the value of the population’s parameters—the so-called “null” hypothesis—and design experiments or observational studies to generate quantifiable data that can be used to test it. After observation, the data are compared to the null hypothesis’ assumptions using a probability measure known as the p-value. This comparative procedure first assumes a probability model for the underlying population, then evaluates whether the data collected are expected or probable outcomes of that population, and thus whether the null hypothesis is (plausibly) true. 

A large p-value, usually greater than 0.05, indicates that the data are not extreme and “fails to reject” the null hypothesis. By contrast, a small or “significant” p-value, usually less than 0.05, indicates that the data are extreme and have a low probability with respect to the assumptions stated in the null hypothesis. In this case, investigators may “reject the null hypothesis” in favour of an alternative hypothesis. In short, to arbitrate between hypotheses, NHST uses *the probability that the stated null hypothesis generated the data*. 

Although this approach is one of the most widely used inferential frameworks across the sciences, it has had its share of criticism [e.g., @gelman_multilevel_2006; @vidgen_p-values_2016; @gelman_failure_2018]. For example, statisticians have recently targeted p-values mainly for their arbitrariness and misuse [@wasserstein_moving_2019]. Although some mistake statistical significance for practical significance [e.g., @kramer_sibling_2016], the interpretation of significant p-values, in terms of rejecting the null hypothesis, is well understood. However, how to interpret non-significant p-values is less clear. Similarly, the NHST toolkit does not include acceptance of a null hypothesis. Nevertheless, some misunderstand this point and attempt to use NHST to verify their null hypotheses. 

Language appears to be part of the problem here, but failing to reject a null hypothesis is not synonymous with accepting it. Instead, “failing to reject” means that there is not enough evidence to invalidate the null hypothesis. Moreover, the relationship between probabilities and alternative hypotheses is not clear and is often misunderstood [@benjamin_three_2019]. In particular, it is challenging to evaluate multiple alternative hypotheses within the NHST framework. Indeed, the ability to assign probabilities to multiple hypotheses in light of the data is one of the many reasons researchers have turned to Bayesian statistics.


## BAYESIAN STATISTICS

During the late twentieth century, scientists popularized Bayesian inference, a statistical approach based on developments made in the eighteenth century by Reverend Thomas @bayes_essay_1763. Bayes was an English Presbyterian minister and mathematician who solved problems in probability involving conditional and prior probabilities [@bellhouse_reverend_2004]. Soon after the popularization of Bayesian inference in the sciences, archaeologists also incorporated Bayesian methods into their toolkits to evaluate hypotheses [e.g., @buck_bayesian_1996]. Today, Bayesian methods have proliferated throughout the scientific literature, including in anthropological and archaeological science [@gelman_bayesian_2020; @otarola-castillo_bayesian_2018; @mcelreath_statistical_2020]. In the past, feasible execution of Bayesian methods was difficult because some calculations are intractable and require intensive computation. Today’s powerful personal computers and high-speed Markov Chain Monte Carlo (MCMC) algorithms, such as the Metropolis-Hastings, Gibbs, and Hamiltonian procedures, have helped to overcome this obstacle and further popularize the approach [e.g., @howson_scientific_2006 :xi; @robert_short_2011; @dunson_hastings_2020].

Another reason for Bayesian approaches’ increased popularity might be the simplicity of interpreting probabilities compared to the p-values used in NHST [@otarola-castillo_bayesian_2018]. Scientists apply Bayesian inference to compute the probability of a hypothesis directly and thus obtain clearer and more direct interpretations than those available from NHST. Also, as with NHST, the degree to which the given hypothesis supports the data is computed, usually via an explicit probability model, known as a likelihood. We formally define these terms below, but in summary, **the likelihood** is a statistical function whose form is determined by the specific probability model we are using. Crucially, Bayesian inference enables researchers to incorporate their expert (or prior) knowledge about the hypothesis into the statistical analysis. Experts’ **prior** knowledge in a field can be quite valuable; however, it is not often operationalized. Practitioners of Bayesian inference convert prior knowledge into **prior probabilities** and use them as part of statistical analyses. Once the prior probability has been determined, as with NHST, new data are observed to test the hypothesis. The likelihood is combined with (or weighted by) the prior to give the **Bayesian posterior distribution**. From this, the probability of the hypothesis given the observed data and the prior knowledge can be computed [@buck_bayesian_1996]. These steps, including the formalization of a simple prior probability, likelihood, and computation of the posterior will be exemplified below in a simple archaeological example.

The primary advantage of Bayesian statistics over NHST is the clarity of the inferences drawn from the analysis. Furthermore, by formally including previous experience or expert information, prior probabilities offer practical improvements over NHST, typically reducing uncertainty in the conclusions reached [@cowgill_past_2001]. Including prior knowledge produces a comprehensive understanding of the proposed hypothesis’ relevance to a larger body of knowledge. Moreover, incorporating prior probabilities enables Bayesian inferences to be “updated,” creating a cyclical effect as current knowledge becomes prior knowledge for future studies. Perhaps Dennis @lindley_bayesian_1972 best summarized the Bayesian learning process by writing the aphorism “today’s posterior is tomorrow’s prior”. Helpfully, it is also possible to use what is known as a flat, vague, or uninformative prior (as we do in our example below) in situations where little or no expert prior knowledge is available, but one may wish to take advantage of the other features of the Bayesian framework.

To further contextualize the application of Bayesian statistics, we provide an example that illustrates how one can use Bayesian statistics to select a hypothesis and solve an archaeological research problem. The example demonstrates how archaeologists can make probabilistic inferences using data and simple prior information about a hypothesis, how to evaluate the uncertainty surrounding a hypothesis, why this approach seems less ambiguous than NHST, and thus why it is becoming increasingly popular. We also formally define the Bayesian framework and review recent Bayesian statistics applications in the archaeological literature.

\newpage









## A SIMPLE ARCHAEOLOGICAL EXAMPLE



@otarola-castillo_bayesian_2018 introduced a simple example to contrast NHST and Bayesian inference. They presented an artificial case study where an archaeologist proposed to infer projectile propelling technology from its relationship to stone projectile morphology. In their example, the archaeologist used the known relationship between projectile point propelling technology and point size, from an ethnographic context. The archaeologist used this relationship as a frame of reference to infer the propelling technology of a sample of stone projectile points recovered from a multi-component archaeological site. Using known measurements of each technology type, @otarola-castillo_bayesian_2018 demonstrated how the archaeologist could use NHST and a Bayesian framework to infer the most likely propelling technology (Table 1). 



> **Table 1** *Summary statistics (mean and standard deviation) of artificial maximum projectile point lengths recovered from the Early and Late Period archaeological contexts, along with equivalent summaries of the maximum point lengths known to be associated with different propelling technologies. The latter are used to define the hypotheses to be evaluated using the archaeological data.*

**Archaeological Projectile Data**

                  Early Period  Late Period                  
----------------  ------------- -------------  --------------
Mean Length (cm) 	    6.1          13                        
SD (cm)          	     2          3.2                        
N                     10           9                         

**Propelling Hypotheses**

                     Arrow         Dart           Spear                
----------------  ------------- -------------  --------------
Mean Length (cm) 	    6.9           11              14                        
SD (cm)          	     2            2               2


The simulated data are maximum length measurements of projectile points from the Early (N=10) and Late (N=9) components of an archaeological site (upper part of Table 1). The archaeologist also measured the maximum lengths of a large sample of ethnographic projectile points with known propelling technology, summarized in the lower part of Table 1 by their means and standard deviations. The hypotheses to be tested are that the archaeological data from the Late and Early Period derive from each of the three ethnographically observed propelling technologies: 1) bow and arrow, 2) atlatl and dart, and 3) hand-thrown spear.  

### Analysis using NHST

The archaeologist tested the hypotheses that the archaeological data were plausible given the ethnographic data relating to each propelling technology. To do this, they used the means () in Table 1 and formalized the hypotheses shown in Table 2. 

> **Table 2**  *Null and alternative hypotheses used for NHST.*

**H~0~- the null hypotheses**

Early Period                           Late Period
------------------------------------   ------------------------------------
$\mu$~Early~ ~Period~ = $\mu$~Arrow~   $\mu$~Late~ ~Period~ = $\mu$~Arrow~
$\mu$~Early~ ~Period~ = $\mu$~Dart~    $\mu$~Late~ ~Period~ = $\mu$~Dart~
$\mu$~Early~ ~Period~ = $\mu$~Spear~   $\mu$~Late~ ~Period~ = $\mu$~Spear~
------------------------------------   ------------------------------------


**H~A~- the alternative hypotheses**

Early Period                                 Late Period
------------------------------------------   ------------------------------------------
$\mu$~Early~ ~Period~ $\not=$ $\mu$~Arrow~   $\mu$~Late~ ~Period~ $\not=$ $\mu$~Arrow~
$\mu$~Early~ ~Period~ $\not=$ $\mu$~Dart~    $\mu$~Late~ ~Period~ $\not=$ $\mu$~Dart~
$\mu$~Early~ ~Period~ $\not=$ $\mu$~Spear~   $\mu$~Late~ ~Period~ $\not=$ $\mu$~Spear~
------------------------------------------   ------------------------------------------



They then assumed that the summaries in Table 1 were for samples from populations distributed under “Normal” probability models and applied the well-known **z**-test [@diez_open_2019: 134]. The same Normal probability model assumptions will also be useful to generate the likelihood function in the Bayesian analysis, later on. Knowing the means and standard deviations of the ethnographic and archaeological data, @otarola-castillo_bayesian_2018's archaeologist computed the **z**-scores and their associated **p**-values (Table 3). 

\newpage
> **Table 3**  *Results of the **z**-score hypothesis tests described in the text, including the associated  **p**-values.* 

**Early Period**

            z-score     p-value    
----------- ----------- -------------
Arrow       -1.26       0.21         
Dart Tips   -7.75       <0.001       
Spear Tips  -12.49      <0.001       
----------- ----------- -------------

**Late Period**

            z-score     p-value    
----------- ----------- -------------
Arrow       5.71        <0.001         
Dart Tips   1.87        0.06       
Spear Tips  0.94        0.35       
----------- ----------- -------------


Using this method, because the p-values were less than 0.001, they rejected the null hypotheses that the means of the Early Period projectile points resembled those of darts or spears (Tables 2 and 3). Instead, the archaeologist determined that the points may have come from a population of arrow projectile points because the associated p-value is greater than 0.05 (Table 3). Thus, there was not enough evidence to reject this null hypothesis. NHST allows the archaeologist to infer that *“the Early Period sample does not have a low probability of resulting from a population of arrow tips,”* and they do not reject this hypothesis. 

![Figure 1  Likelihoods of the maximum length data. The red dashed lines illustrate the “Normal” likelihood of the maximum lengths data measurements obtained empirically from the archaeological Early (top) and Late (bottom) periods. The likelihood values were obtained after estimating the parameters of the Normal probability distribution that maximized the likelihood of the measurement values (i.e., Maximum Likelihood Estimation, MLE). Following this procedure, we used the MLE parameter estimates to simulate the likelihood of hypothetical maximum length values greater than the range observed archaeologically. The black solid line depicts these values. In both panels, we overlaid the empirical (gray dotted) over the hypothetical (black solid) likelihood estimates for comparison](The-Bayesian-Inferential-Paradigm-in-Archaeology-rmarkdown_files/figure-latex/Fig1-1.pdf) 


Following this exact procedure for the Late Period, the archaeologist obtained a p-value less than 0.001 for the arrow hypothesis. However, the **p**-values for the speartip and dart tip hypotheses are both greater than 0.05. Therefore, although the archaeologist may reject the arrow hypothesis, the inference cannot be distinguished between *“the sample does not have a low probability of resulting from a population of dart tips”* and *“the sample does not have a low probability of resulting from a population of spear tips”*. 

### Bayesian analysis
@otarola-castillo_bayesian_2018's archaeologist then compared the NHST analysis to one using a Bayesian framework. The authors did this to show how archaeologists might apply Bayesian statistics to assign probabilities to the hypotheses that the archaeological projectile points were arrows, dart tips, or spear tips - given the data in hand. 

This approach is advantageous when a scientist uses multiple working hypotheses and is interested in deciding which is most probably supported by the data. The Bayesian framework can achieve this goal by using the same assumptions about the underlying probability distributions as those in the NHST approach. Using Bayes' theorem, one may then represent prior knowledge as a corresponding prior probability distribution and calculate each hypothesis's posterior probability. 

To conduct this analysis, Otárola-Castillo and Torquato followed the procedures on likelihoods, prior and posterior probabilities, and MCMC sampling we outlined in our Bayesian Statistics section above. For additional technical detail, we refer the reader to the What is Bayes’ Theorem section below. The authors modelled the likelihood of the maximum projectile length using the “Normal” probability model (Figure 1). They also modelled prior knowledge using a uniform probability distribution to reflect no previous information and demonstrate the probabilistic approach to hypothesis selection. Under the uniform distribution, the prior probabilities of all maximum projectile lengths were identical. Together, the likelihood and prior probability models are foundational components of Bayesian Inference.

The archaeologist in @otarola-castillo_bayesian_2018 then used an MCMC procedure to calculate the probability of each hypothesis: that the archaeological samples were either arrow, dart, or spear, applying a two-step process. First, they generated samples from the posterior distribution via MCMC. Second, they compared the sampled values to intervals defined by one standard deviation around the mean of the ethnographically observed values for each of the point types (Table 4, Figure 2). In this way, sampled posterior point lengths that lay between 4.9 cm and 8.9 cm were defined (a posteriori) as Arrows; those in the range 9 to 13 cm Darts; those in 12 to 16 cm Spears. Point lengths outside the range of 4.6 to 16 cm were outside of the evaluated hypotheses. Therefore, they were declared to belong to a group labelled "Other". There is some overlap between the summary probability distributions implied by the ethnographic data. Thus, the hypotheses are not mutually exclusive. In other words, due to overlapping measurements, some projectile points may be consistent with more than one hypothesis. We discuss the implications of this overlap below.

Next, the archaeologist calculated the posterior probabilities by dividing the number of projectile points consistent with each hypothesis by the total number of projectile points for each period. The posterior probability of point lengths for each hypothesis is reported in Table 4 and illustrated in Figure 2. Since the hypotheses are non-mutually exclusive, the posterior probabilities corresponding to each hypothesis within a period are not expected to sum to 1. Depending on one’s hypotheses, the interpretation of probabilities relating to non-mutually exclusive outcomes may be problematic. For example, one might ask, what is the probability that the projectile points are Arrows or Darts? In this case, because some Arrows may be similar in length to Darts, these are not mutually exclusive outcomes, and one may not simply add their respective probabilities together. The solution is to use the General Addition Rule of probability (see @diez_open_2019: 83-88). We do not evaluate such an hypothesis in this example but note this rule so that readers may adopt it if needed for their own work.

Using the resulting Bayesian posterior probability distribution to conduct inference lets scientists make fully probabilistic statements about their hypotheses and thus make more explicit comparisons than those provided by the NHST framework. The results highlighted by Figure 2 seem clear regarding the probability of each hypothesis. We will discuss these further. After examining the resulting posterior probabilities, the archaeologist determined that the Early period sample points were most probably used as arrows (with probability 0.97) and likely propelled by a bow-like mechanism. This mode of stone point propelling changed during the Late Period when the people living on this site began to use mainly hand-thrown spears (with probability 0.89). 

In this way, the Bayesian approach to testing  hypotheses leads to results that are more readily interpreted than those via the p-value based NHST. In particular, we are  provided with measures of probability that the data support the hypotheses, which have considerably more intuitive interpretation than those provided by p-values.

\newpage
>**Table 4** *Posterior probabilities that the Early and Late Period maximum projectile point lengths were associated with arrow, dart, and spear propelling technologies.* 


Function    Mean±SD of max. point length     Early Period            Late Period
----------- -------------------------------- ----------------------- ------------------
Arrow       6.9 ± 2                          0.97                    0.0009
Dart Tips   11 ± 2                           0.004                   0.17
Spear Tips  14 ± 2                           0.00002                 0.89
----------- --------------------------------- ----------------------- ------------------


![Bayesian posterior probability distributions of each of three propelling technology hypotheses: a) Arrow, b) Dart, c) Spear in the Early (bottom) and Late (top) periods. The amount of area under the curve reflects the probability of each hypothesis expressed as percentages.](The-Bayesian-Inferential-Paradigm-in-Archaeology-rmarkdown_files/figure-latex/Fig2-1.pdf) 

\newpage







## \hfil WHAT IS BAYES’ THEOREM\hfil

Bayes’ theorem is an algorithm for obtaining the value of a conditional probability statement, when one knows its inverse. It is usually exemplified by considering two related events, A and B. Put simply, Bayes’ theorem states that (equation 1):

\begin{equation}
P(A|B) = \frac{P(B|A)\cdot P(A)}{P(B)}
\label{eg:1}
\end{equation}

In this case, to obtain the conditional probability of A given B, P(A|B) - here P represents probability and | is read as ‘given’ - one needs to divide the joint probability of A and B, P(A and B), by the marginal probability of B, P(B). The product of P(B|A) and P(A) is the joint probability P(A and B). The formula then generalizes to equation (2):

\begin{equation}
P(A|B) = \frac{P(A \cap B)}{P(B)}
\label{eg:2}
\end{equation}

where the joint probability is divided by the marginal P(B). Statisticians call P(A|B) the posterior probability of A given B, P(B|A) the inverse conditional (or likelihood) of B given A, and P(A) the prior probability of A.

### The link between Bayes' theorem, inference, data and hypotheses

The simulated archaeological scenario above provided a tangible example of the different components of a Bayesian analysis, including an event’s probability, the probability of one event given another, prior and posterior probabilities. Although the procedure here is specific to archaeological data, Bayes’ theorem is a very general algorithm that is useful for a wide variety of data and data-generating processes. This section generalizes Bayes’ theorem to a variety of other scenarios. 

We stated earlier that Bayesian statistics uses the data in hand, (D), to assign probabilities to hypotheses about a population (H). The statement P(H|D), i.e., the probability of the hypothesis given the data, formalizes this relationship. To operationalize this statement in the context of data and hypotheses, Bayes’ theorem functions as

\begin{equation}
P(H|D) = \frac{P(D|H)\cdot P(H)}{P(D)}
\label{eg:3}
\end{equation}


where: P(H|D) is the posterior probability — the probability of the hypothesis given the data in hand; P(D|H) is the probability of the data given the hypothesis, or the “likelihood” of the observed data; P(H) is the prior probability of the hypothesis (before the data were observed), and P(D) is the probability of the data in hand (out of all possible values of the data). Alternatively, using modern statistical vernacular this operation can then be expressed in a slightly different form as:


\begin{equation}
Posterior  = \frac{Likelihood \cdot Prior}{P(Data)}
\label{eg:4}
\end{equation}


In Otárola-Castillo and Torquato’s artificial example, the hypotheses represented the belief that the observed Early and Late period projectile point data represented samples from populations derived from particular propelling technologies. The data were modelled by the Normal probability distribution, and the hypotheses were characterized by the values of the model’s parameters. 

We use the symbol x to represent the observed data and the symbol $\theta$ to represent the parameter(s) of our model of the population that we are trying to learn about. Given x and a model with parameter(s) $\theta$, we can more formally describe Bayes’ theorem and its three components: the *likelihood*, the *prior*, and the *posterior*.

i. The *likelihood* is a statistical function. Its form is determined by the specific probability model we are using but, in general terms it is represented by P(x|$\theta$). Consequently, the likelihood is the probability of observing particular data values given some specific values of the unknown parameters. Thus, this is a formal statement of the relationship between what we want to learn and the data we collect.

ii. The *prior* is also a function and can be represented by P($\theta$). In simple terms, we can think of this as the probability we attach to observing specified values of the unknown parameters before (*a priori*) we observe the data. In other words, this is a formal statement of what we knew before the latest data were collected.

iii. The posterior is the probability distribution that we want to obtain (a combination of the information contained in the data, the likelihood and the prior) and can be represented by P($\theta$|x). Put plainly, this is the probability we attach to specified values of the unknown parameters after observing the data. In this more technical context, we can express Bayes’ theorem as:

\begin{equation}
P(\theta|x) = \frac{P(x|\theta)\cdot P(\theta)}{P(x)}
\label{eg:5}
\end{equation}

In addition, the numerator, the product of the likelihood and the prior probability without the normalizing denominator P(*x*)is proportional to ($\propto$) the posterior and is often computed and expressed by 

\begin{equation}     
P(\theta|x) \propto P(x| \theta) \cdot P(\theta)
\label{eg:6}
\end{equation}

or,

\begin{equation}
Posterior \propto Likelihood \cdot Prior
\label{eg:7}
\end{equation}

In this manner, Bayesian statistics offers an alternative statistical framework for evaluating hypotheses through a mechanism for obtaining *a posteriori* information about the parameter values of interest, based upon the data, a model, and appropriately formulated prior information. In other words, given an explicit statement of our *a priori* information, a clearly defined statistical model and a desire to obtain *a posteriori* understanding, Bayes’ theorem provides us with a probabilistic framework within which to make interpretations.

In addition to the coherent and explicit nature of the framework, there is another attractive feature of adopting the Bayesian paradigm in that it allows us to learn from experience. Priors enable the explicit contextualization of previous knowledge or beliefs about the topic under investigation [@cowgill_distinguished_1993; @buck_bayesian_1996]. This should be a natural feature to archaeologists for whom context is quite meaningful, or as @buck_bayesian_1996 discuss, archaeologists interpret the discovery of new artifacts in conjunction with artifacts that have already been discovered.

Moreover, today’s posterior information (based on current data and prior information) is in a suitable form to become the prior for further work if and when more data become available. Few other interpretative frameworks offer a clear structure for updating one’s beliefs in the light of new information and yet it is such an important part of most intuitive approaches to learning about the world in which we live.
\newpage







## \hfil OTHER ARCHAEOLOGICAL APPLICATIONS\hfil

### Chronological modelling
The reliable construction of chronologies is an integral part of all archaeological research. Consequently, an abundance of research has been conducted to create robust chronologies and thus, assist archaeologists in interpreting past events. Early work laid the foundation for the use of Bayesian methods in chronological modelling to improve precision [@naylor_archaeological_1988; @buck_combining_1991; @buck_calibration_1992]. The advent and continued improvement of user-friendly modelling software, including BCal [@buck_bcal_1999] and OxCal [@bronk_ramsey_analysis_1994; @bronk_ramsey_methods_2017], has enabled many archaeologists to employ Bayesian chronological modelling in their research. In fact, the construction of chronologies has been described as the one archaeological application of Bayesian methods that is now routine [@buck_being_2015].

There has been a documented increase in the use of Bayesian chronological modelling over the last decade [@bayliss_quality_2015; @hamilton_myths_2018], as numerous studies have re-examined radiocarbon dates to refine regional chronologies. Although these methods were initially used by archaeologists in the United Kingdom [@hamilton_myths_2018], Bayesian chronological studies have now been conducted in nearly every region of archaeological interest, including:

i. Central America [@inomata_high-precision_2017; @mendelsohn_chronology_2018; @tsukamoto_building_2020]; 
ii. South America [@marsh_dating_2017; @wynveldt_late_2017],
iii. Europe [@arvaniti_tracing_2018; @jimenez_cultural_2018; @krajcarz_towards_2018; @manning_new_2018; @ricci_chronological_2018; @paulsson_radiocarbon_2019],
iv. Asia [@long_bayesian_2017; @ricci_chronological_2018; @birch-chapman_bayesian_2019; @yang_refined_2019],
v. Africa [@kramer_sibling_2016; @brandt_new_2017; @sadr_new_2017; @loftus_archaeological_2019], and 
vi. Oceania [@brockwell_new_2017; @kirch_new_2017; @urwin_chronology_2018; @david_dating_2019].
 
Indeed, even those archaeologists who simply report individual, calibrated radiocarbon dates are now reliant on Bayesian methods since the most recent estimates of the radiocarbon calibration curves (IntCal20, SHCal20, and Marine20) are grounded in Bayesian inference. They were constructed using a Bayesian spline approach to combine data from tree rings, floating tree-ring chronologies, lacustrine and marine sediments, speleothems, and corals [@reimer_intcal20_2020].

Archaeologists have applied Bayesian methods to other methods of absolute dating. For example, recent studies have constructed chronological models using optically-stimulated luminescence (OSL) dates [@clarkson_human_2017; @combes_bayesian_2017; @veth_early_2017; @jimenez_cultural_2018; @demuro_corrigendum_2019; @heydari_bayesian_2020], and dendrochronology [@millard_bayesian_2002; @hassan_simple_2019; @lorentzen_shipbuilding_2020].
 
Perhaps most significantly, Bayesian chronological modelling enables archaeologists to include numerous sources of archaeological dates in a single interpretive framework, including those drawn from relative dating and absolute dating, to create chronologies of hard-to-date contexts. By combining relative dating and absolute dating methods with Bayesian modelling, archaeologists can produce more precise and accurate dates [@cowgill_we_2015]. For example, @croix_dating_2019 combined artifact chronologies, coin dates, and radiocarbon dating in a Bayesian model to date earthworks in Denmark. Prior to this research, dating these structures was difficult due to the limited survival of dateable artifacts and the reuse of building materials in antiquity. By constructing a Bayesian chronological model using coin age and radiocarbon dates, researchers improved the dating precision of the earthworks. Furthermore, @dinapoli_model-based_2020 used a Bayesian modelling approach to combine radiocarbon dates, stratigraphy, and ethnohistoric accounts to examine the collapse and resilience of populations on Rapa Nui. Other examples of studies include those combining absolute dating methods [e.g., @anyon_re-evaluating_2017; @fitzsimmons_chronological_2017; @smith_puntutjarpa_2017] and those drawing on relative and absolute dating methods [e.g., @guerin_chronology_2017; @douka_age_2019].
 
Other studies have used Bayesian modelling to clarify the complex relationship between humans and the environment. For example, Banks and colleagues (2019) utilized Bayesian hierarchical modelling to determine the date for cultures from Upper Palaeolithic France. These dates were then compared to palaeoecological records to determine the palaeoclimatic variability during each period. Similarly, @kearney_vegetation_2019 used Bayesian methods to combine archaeological and palaeoecological chronologies in a study examining the connection between vegetation changes and human activity near a megalithic tomb dating to the Neolithic in Ireland. Using this method, he was able to determine if significant palynological events occurred before, after or during the construction and use of the tomb. Ultimately, he determined that the clearing of the woodland occurred prior to the construction of the megalith. 
 
### Artifact analysis

Bayesian inference has been applied in numerous ways to study a broad array of artifacts, including ceramics, bone and stone tools. Early applications examined the provenance of artifacts and ceramic seriation [e.g., @buck_computational_1990; @buck_bayesian_1996;  @halekoh_bayesian_1999; @robertson_spatial_1999]. Continued research examining ceramics has utilized Bayesian modelling of radiocarbon dates to determine the chronologies of ceramic artifacts by combining absolute dating and studies of ceramic typologies [e.g., @naylor_archaeological_1988]. Similar methods have been used to examine ceramic traditions in Europe [@krol_chronology_2020], Bolivia [@marsh_temporal_2019], Guatemala [@arroyo_refining_2020], and Papua New Guinea [@skelly_changing_2018]. The combination of chronological modelling and ceramic data has been used to examine the dispersal and spread of ceramic cultures [e.g., @mehault_applying_2017; @binder_modelling_2018]. 
 
Recently, the application of Bayesian modelling to ceramic analysis has extended beyond seriation. For example, @fernandes_reconstruction_2018 used a Bayesian approach to identify the types of food that created residues in prehistoric European pottery. By analysing carbon isotope measurements and comparing them with measurements from known sources, the authors determined which foods had contributed to the residues and thus how the pots had been used. Since pots are reused to prepare multiple types of foods, results can be ambiguous when identifying the foods contributing to residues. The use of Bayesian methods addressed this ambiguity by estimating the contribution of various food types to the residues. 
 
Furthermore, Bayesian methods are becoming integral in the study of stone and bone tools. Researchers have used Bayesian methods to test hypotheses about stone tool assemblages [e.g., @marwick_early_2016] and develop techniques for studying stone tools. These techniques allow researchers to assign probabilities to the phenomenon being studied. For example, @murray_new_2020 developed a novel method combining 3D microscopic analyses of surface roughness and a Bayesian probability model to evaluate if Middle Stone Age silcrete tools from Pinnacle Point 13B (South Africa) had been heat treated. The model measured the probability that a tool has been heat treated,allowed for the continued updating from future heat treatment experiments, and performed with high accuracy. Similarly, other researchers combined a taphonomic analysis of the surface of unworked bone and bone tools with multivariate Bayesian modelling to quantify the taphonomic changes on the surfaces of the unworked and worked bones to accurately predict the original surface of the bone tools [@martisius_time_2018; @martisius_method_2020].
 
### Zooarchaeology

Researchers have used Bayesian statistics to study zooarchaeological trends. Pioneering work by @fisher_mastodont_1987 used Bayesian inference to determine whether scavenging or hunting led to the creation of butchery marks on proboscidean assemblages. Recent work has focused on studying seasonality and domestication. For example, @parkington_contemporaneity_2020 used a Bayesian approach to study the seasonal use of Later Stone Age archaeological sites in South Africa. By reanalysing their previous studies on the timing of death using a Bayesian framework, they were able to determine, with greater accuracy, when hunter-gatherers would have used the sites where seal remains were found. Additionally, scholars have used Bayesian methods to construct phylogenies examining the domestication of animals, including swamp buffalo [@wang_whole_2017] and pigs [@xiang_origin_2017]. Other research has examined the foods consumed by domesticated animals. @blanz_identifying_2020 used Bayesian modelling to examine the diets of modern sheep, specifically the amount of seaweed consumed, which can be used as a reference sample for identifying similar consumption patterns in archaeological contexts. 

Additionally, archaeologists have used Bayesian methods to study faunal assemblages and make inferences about their use. For example, @osborn_bayesian_2019 constructed a Bayesian network model using ethnographic, ethnohistoric, and archaeological data to determine whether Andean faunal assemblages indicated feasting, sacrifice, or daily refuse. The primary benefit of using a Bayesian approach in the study was the resulting replicable analysis that eliminates the subjectivity present in interpreting faunal assemblages. Rather, this method reports the probabilities of the faunal assemblage representing each type of behaviour. Furthermore, @baumann_role_2020 used Bayesian methods to estimate the abundance of foxes and hares in Palaeolithic Europe to determine how their abundance changed over time as they were hunted by humans for their meat, fur, and teeth. The use of Bayesian methods in this study allowed the researchers to overcome a small sample size while modelling animal abundance.
 
Bayesian techniques have been used to develop and re-examine the methods used in zooarchaeological research. Researchers have used Bayesian inference to develop a reliable and replicable probabilistic method to distinguish between sheep and goat bones in archaeological contexts [@wolfhagen_probabilistic_2017]. Since goats and sheep are very similar species that share many traits, it can be difficult to distinguish between them. This method provides the probability that a specimen is a goat given the identified traits. Furthermore, @wolfhagen_re-examining_2020 has re-examined the “logarithm size index” (LSI), a method for comparing the body sizes of animals between assemblages that is typically used in studies of animal domestication. He suggests adopting Bayesian multilevel LSI models to examine hypotheses about faunal assemblages.
 
### Bioarchaeology 

The use of Bayesian methods in bioarchaeological analyses was pioneered by Konigsberg and colleagues for studying age-at-death and stature estimation [e.g., @konigsberg_estimation_1992; @konigsberg_paleodemography_1994; @lucy_bayesian_1996; @konigsberg_stature_1998]. Recent research has continued to apply Bayesian statistics to the construction of biological profiles. For example, @anzellini_estimating_2019 proposed the use of Bayesian logistic regression to account for uncertainty in the sample when estimating the sex of individuals found in commingled contexts in the Andes. Although the frequentist and Bayesian approaches produced similar results, the authors demonstrated the validity of using Bayesian methods to account for uncertainty and to produce usable demographic profiles in bioarchaeological studies. Furthermore, @rosenstock_human_2019 used Bayesian additive mixed modelling to examine the global spatiotemporal trend in stature. This method enabled the researchers to account for spatiotemporally patchy data as well as fragmentary skeletal samples.
 
Further studies have utilized Bayesian mixing models to reconstruct prehistoric diets. Typically, these methods have used carbon and nitrogen stable isotope data to determine the types of foods people were eating. One popular method is called the Food Reconstruction Using Isotopic Transferred Signals (FRUITS) approach, which can account for multiple dietary sources and the uncertainty inherent in dietary inference. For example, @pezo-lanfranco_middle_2018 used Bayesian mixing models to quantify the proportion of three sources of food: plants, marine mammals, and terrestrial mammals. They determined that the people of the Atlantic Forest of South America consumed a large amount of carbohydrates, suggesting a unique diet compared to other populations in the area during the Middle Holocene. Using various Bayesian mixing models, other studies have examined prehistoric dietary trends in Europe [@bownes_using_2017; @sjogren_modelling_2017; @boethius_fish_2018;  @cubas_long-term_2019], South America [@gordon_dietary_2018], and Africa [@maurer_geochemical_2017]. Recent studies have used similar Bayesian modelling to study prehistoric weaning trends [@king_comparison_2017]. Specifically, using the FRUITS method, @de_angelis_dietary_2020 reconstructed the diet of those buried at the Quarto Cappello del Prete. From this reconstruction, they determined that Roman children were weaned around three years of age.

Other researchers have used mixed/multilevel/hierarchical modelling approaches. For example, @perri_dietary_2019 examined the canine diet as a proxy for human diets in archaeological contexts in Nicaragua. To infer the probability of the model’s parameters the authors used a Bayesian approach including MCMC to estimate the denominator of Bayes theorem. Hierarchical models in this context are flexible and scalable [@gelman_data_2006]. They can include individual and group level data in a model. This flexibility  provides improved inference on the parameters in question, resulting  in more accurate estimates of the model’s parameters [@katahira_how_2016]. 

### Spatial archaeology 

By combining prior knowledge regarding geographical data, archaeologists have been able to study spatial trends (see Chapter xx). For example, researchers have used Bayesian methods to examine the placement of archaeological sites on the landscape [@wright_analysis_2014] and predict the locations and settlement patterns of archaeological sites [@ortman_empirical_2007; @stewart_novel_2017]. Other research has incorporated Bayesian chronological modelling into spatial archaeological analyses. For example, @snitker_patch-based_2018 combined prehistoric land use maps generated by surveys, chronological data, and Bayesian methods to examine shifting occupation and land use patterns in Spain. The use of Bayesian methods in this study was critical as it allowed the researchers to make probabilistic inferences regarding the most likely occupation period at archaeological sites that may have been reused throughout history. Similarly, @wright_spatial_2020 used Bayesian chronological modelling of radiocarbon dates to construct a summed probability distribution estimating occupation events in the Baekje Kingdom of Korea during the Three Kingdoms Period (57 BCE to 688 CE). The researchers proceeded to use these data as part of a larger model examining the spatial distribution and dynamics of human activity areas over time. These methods allowed the researchers to make probabilistic statements about settlement patterns’ hypotheses at a time when occupation patterns were thought to be changing. 
\newpage







## \hfil SOME PRACTICALITIES\hfil


### Modelling

Although numerous probability models exist, many archaeological problems are statistically non-standard. This has often meant that the close collaboration of a number of specialists, including statisticians, is required to build useful models. Fortunately, statisticians have often found archaeological problems to be interesting and challenging and so this kind of collaboration is not too unusual. Nonetheless, although applications of Bayesian analysis to archaeology have been around for more than 30 years, they are by no means ubiquitous and further collaboration is certainly needed.

### Specifying the prior

One of the major stumbling blocks to the more widespread use of Bayesian techniques in archaeology is the perceived difficulty of specifying prior information. Some archaeologists do not acknowledge that reliable prior information exists and others have philosophical objections to the use of subjective opinions in formal inference. Both such groups typically prefer to continue using exploratory methods or traditional NHST-based ones. Others have expert knowledge and would like to use it, but have difficulty expressing their ideas in a suitable form because of their lack of knowledge about the mathematics that underlie the models they wish to use. Tackling this problem requires further collaboration, clear communication, and an acceptance that different researchers will have varying views on which interpretive framework to use or which specific model to adopt. Most importantly, there is no need for everyone to agree. Researchers who adopt the Bayesian framework are forced to be explicit about what they believe. As a result, different workers can compute posteriors based on their own prior information and compare them formally with the inferences of others.

### Evaluating the posteriors

Early applications of the Bayesian framework to archaeology (as with other disciplines) were restricted to likelihoods and priors for which the necessary calculations could easily be undertaken. However, since the mathematical integrations required for some models are not analytically soluble, a fair number of real questions simply could not be tackled. These problems have now largely been overcome by the widespread adoption of numerical techniques that allow the posterior information to be sampled rather than obtained exactly. Some of the earliest illustrations of the use of these techniques for evaluating Bayesian posteriors were in Bayesian radiocarbon calibration [@buck_calibration_1992; @buck_bcal_1999; @litton_archaeological_1996]. Advances in algorithms to create and sample from Markov chain Monte Carlo simulations (MCMC) such as Metropolis-Hastings, Gibbs sampling, and the Hamiltonian procedures such as No U-Turn Sampling (NUTS) [e.g., @dunson_hastings_2020; @hoffman_no-u-turn_2014]  implemented by popular software like BUGS, JAGS, and STAN [@gilks_language_1994; @plummer_jags_2003; @sturtz_r2winbugs_2005; @team_rstan_2019] have helped to alleviate this problem. 

### Interpretation
Ultimately, the most important part of any statistical investigation is the interpretation of the results obtained. The posterior distributions that arise from Bayesian analyses can be very complex and are sometimes not directly interpretable in terms of the original problem. This means that exploratory methods of data analysis may be needed to help investigate, interpret, and report upon the posterior distributions obtained. When making such interpretations, the level of confidence in the posteriors is affected by their sensitivity to changes in the data, priors, or model. Such sensitivity should be investigated as part of the interpretation of all posterior information. It is always useful to relax some of the prior assumptions and re-compute the posteriors to see what effect this has. All reports of Bayesian analyses should make reference to sensitivity analyses of this type, since without them we cannot be sure how robust the results are and thus how reliable they would be as prior information for future research.
\newpage







## \hfil HOPES FOR THE FUTURE\hfil

We have discussed the positive contributions of Bayesian inference to archaeological thinking. In addition to providing a fully probabilistic framework, Bayesian statistics requires that one makes existing prior knowledge explicit to use in statistical analyses. By doing so, scientists take advantage of a more comprehensive set of information when evaluating hypotheses. This is a major advantage over NHST and the related Maximum Likelihood, and Information Theory approaches to model-selection [@murtaugh_defense_2014]. Increases in the popularity of Bayesian applications in archaeology are likely due to the recognition of these features. To continue this trend, we outline an ambitious set of initiatives we hope to see in the future of Bayesian applications in archaeology. 

### A framework for archaeological science

The Bayesian approach provides a systematic learning procedure, using evidence to update one’s beliefs or hypotheses until reaching a confident and accurate level of knowledge. This evidence-based learning approach inherently resembles the scientific process of hypothesis generation and evaluation. As a science, data-laden inference about the past is also inherent to archaeology. New knowledge from archaeological data recovery through excavation, survey, or analytical activities constantly update archaeologists’ state of knowledge and revise the degree of support for prior hypotheses (e.g., the initial colonization of the Americas and out of Africa origins of *Homo sapiens*). 

### Increase diversity of Bayesian applications

Gauging by the seemingly exponential increase in the number of Bayesian papers in archaeology in the 2000s to the 2010s [@otarola-castillo_bayesian_2018, Fig 1], not only has the Bayesian inferential framework increased in popularity in the general sciences, but also in archaeology. This jump in usage is also evidenced by the number of Bayesian papers, posters, and symposia at conferences [e.g., @buck_stratification_2020; @krus_big_2020; @wolfhagen_bayesian_2021]. 

The increase in applications is due in part to purpose-written software and libraries, tailored to the needs of archaeologists (e.g., OxCal, BCal, and Bchron [@haslett_simple_2008]). Increasingly, however, as archaeologists become more confident to write their own code, simple-to-use and accessible software like STAN, JAGS, and BUGS [@gilks_language_1994; @plummer_jags_2003; @sturtz_r2winbugs_2005; @team_rstan_2019] are also being adopted. For R users, for example, the RStan package [@team_rstan_2020] has simplified the access to this software, and so has the development of “higher level” code R-packages like Rstanarm and BRMS [@burkner_brms_2017; @goodrich_rstanarm_2020]. 

### Training in underlying theory

With accessibility, however, there is potential for technical sophistication and attention to detail to be missed. Adopting easy-to-access software might hide some of the Bayesian approach’s complexity, comprehension of which is necessary in order for users to  take responsibility for the modelling choices inherent in adopting them. 

As such, one of our hopes for the future is an increase in training opportunities for archaeologists in both the statistical and theoretical details underlying Bayesian inference, and the technical and practical details associated with implementation. In our opinion, greater knowledge of these two steps will generate a deeper understanding and more responsible adoption of the Bayesian framework for inference. 

This leads to the type of student training we hope to see in the future. Training students to become aware of and fluent in the theory underlying NHST and Bayesian inference will need some remodelling to current curricula. Integrating statistical and computational theory into archaeological study programs would be one step towards providing students with the expertise to evaluate and develop reliable Bayesian solutions for themselves. It would, of course, also allow them to evaluate more responsibly the modelling work of others, thus leading to a better informed and more articulate body of reviewers for archaeological journals. 

### The power of algorithmic thinking

Training in probability theory and coding alone will not change a discipline, but together with an encouragement to formalize thinking they might. Archaeologists are widely known for our meticulous record keeping. We propose that archaeologists complement our reputation for high quality documentation, by adding greater formalization to our thinking and hypothesizing. Coders do this out of necessity, but it is not routine practice in most of archaeology. 

There are, of course, widely used and highly regarded field manuals that encourage step-by-step record-keeping [@crow_crow_2001; @hester_field_2016; @white_archaeological_2016] and many modern excavations follow these closely. . However, beyond fieldwork, careful data handling and modelling procedures have traditionally not been given such emphasis, although there are, and have been, notable examples of good practice [e.g., @carlson_quantitative_2017; @mccall_strategies_2018; @banning_archaeologists_2020]. Processes such as phasing a site or interpretation of the archaeological record in an entire landscape, require the handling of very large amounts of information, typically held in many different computer files. The field would benefit if this processing were systematically recorded and replicable. The consequence of not doing this might be an undocumented workflow that even those involved struggle to fully recreate if needed.

Those with coding experience know that poorly documented workflows are not a sustainable approach to information management. What’s needed instead is a step-by-step or flow-diagram approach to planning and documenting the post-excavation workflow. Setting up such approaches is time-consuming, of course, but the advantages for reproducibility are immeasurable. Fortunately, archaeologists are increasingly open to adopting some of these processes [@marwick_computational_2017]. Moreover, there are now several well-established environments that encourage researchers to take this approach. One such is Rmarkdown [@allaire_rmarkdown_2020] which allows users to embed R code and output within a text document. Those of us who use such environments have found that we naturally document the data management and analysis process, as we work, and can write up and archive our work much more quickly and accurately, too. 

\newpage

# REFERENCES 




