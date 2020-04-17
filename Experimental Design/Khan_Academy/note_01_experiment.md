### Experiments
###### video lectures see [Khan Academy](https://www.khanacademy.org/math/statistics-probability/designing-studies/experiments-stats-library/v/introduction-to-experiment-design)

#### experiment design
To examine the **causal relationship** between the **explanatory variable** and the **response variable**.

A **treatment** is the specific level of explanatory variable given to to experiment unit in the experiment, if multiple explanatory variables are involved, a treatment is then the combination of these specific levels from the explanatory variables.

The **experimental unit** is the entity to whom the treatment is assigned and against whom the response variable is measured.

In a **comparative experiment**, the group of units that receive the treatment is called the **treatment group** and the one that does not receive is called **control group**. Random assignment creates roughly similar groups by approximately balancing potentially confounding factors among the groups (might be one control and multiple treatment groups)

**Placebo effect**, unit in the treatment group often respond to any treatment, even in treatment without, in case of pharmaceutical experiments, any therapeutic value, this is known as placebo effect. The **blinding in subject** would help protect against bias from placebo effect.

**Double-blind** (subjects and the physicians / nurses / people that administrate the experiment) will help protect against bias that arise from:
- researcher personal preference towards the treatments/ subjects that might incur other confounding factors
- information leak from researchers to subjects to further induce placebo effect

Even the **triple-blind** experiment where the people analyzing the data do not know who belongs to treatment or control

**Randomized block design** is one of the experiment design that draws from stratified sampling, where experiment units are divided into different blocks based on the confounding factors, units within each block are supposed to more similar than unit from other other blocks.

Another technique, as alternative or supplement to block design, to deal with lurking variables (unobserved) is to use **cross-over design** where the same group of experiment units will receive control for a period of time and then receive treatment for another period of time.

A **matched pair design** is a special case "of a randomized block design. It can be used when the experiment has only two treatment conditions; and subjects can be grouped into pairs, based on some blocking variable. Then, within each pair, subjects are randomly assigned to different treatments."[source](https://stattrek.com/statistics/dictionary.aspx?definition=matched%20pairs%20design)

#### random sampling VS random assignment

|   | random sampling  | NOT random sampling  |
|:-:|:-:|:-:|
| random assignment  |  This experiment could determine **causal relationship** in the **population** | This experiment could determine **causal relationship** for the **selected sample** |
| NOT random assignment  | This experiment could detect **correlation** in the **population** but cannot make causal inferences  |  This experiment could only detect **correlation** in the selected sample |
