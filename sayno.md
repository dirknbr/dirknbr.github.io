# A mathematical model of saying no

Many people struggle to say no when they are asked for a favour or task. 

When you say no you save effort/cost C but you have a potential future (social) cost of being considered not nice $C_{nn}$ and you also forego the potential benefit B from doing the work. 

When you say yes you spend cost C but have a probability P of getting benefit or reward B. 

You discount the future with factor d. 

This is a compelling foundational model. It captures the basic trade-off: Tangible Effort vs. Social Capital.

## The Base Inequality (Formalized)

First, let's establish the decision rule based on the current equilibrium. You should only say "Yes" if the utility of doing so exceeds the utility of saying "No."

$$U(Yes) > U(No)$$

Substituting variables:

$$P \cdot B - C > -d \cdot C_{nn}$$

The "Yes" Threshold:

$$P \cdot B + d \cdot C_{nn} > C$$

Interpretation: You should only say yes if the sum of the potential reward ($P \cdot B$) and the avoided social awkwardness ($d \cdot C_{nn}$) is greater than the effort cost ($C$).

## The Extended Model

Real-world decisions are rarely isolated; they displace other activities and set precedents. We must introduce three new terms:

$O$ (Opportunity Cost): The value of the next best thing you could do with the time/effort $C$.

$\Delta F$ (Future Demand Delta): The change in future requests received based on your answer. Saying "yes" often signals availability, leading to more low-quality requests (the "competence curse").

$\epsilon$ (The Planning Fallacy): We notoriously underestimate the cost $C$ and overestimate the benefit $B$.

The New Equations

Utility of Yes:

$$U(Yes) = (P \cdot B) - (C \cdot (1+\epsilon)) - O + \Delta F_{yes}$$

Note: $\Delta F_{yes}$ is usually negative (future burden).

Note: $C$ is inflated by $\epsilon$ (error margin, typically $1.5x$ to $2x$).

Utility of No:

$$U(No) = -d \cdot C_{nn} + \Delta F_{no}$$

Note: $\Delta F_{no}$ might be positive (people learn to value your time).

The Extended Equilibrium

You are indifferent (and should lean toward "No") when:

$$(P \cdot B) - C(1+\epsilon) - O < -d \cdot C_{nn}$$

Rearranging to solve for The Cost Limit:

$$C < \frac{(P \cdot B) + (d \cdot C_{nn}) - O}{1 + \epsilon}$$

## Key Insights from the Model

A. The "Nice Guy" Trap ($d \cdot C_{nn}$)

The variable $d$ (discount factor) acts differently on $C_{nn}$ than typically expected.

The Problem: The social cost ($C_{nn}$)—the awkwardness of saying no—is immediate. The benefit ($B$) is often in the future.

Hyperbolic Discounting: Humans over-weight immediate pain. We treat $d$ as very high (near 1) for the social cost, but low for the future effort $C$.

Mathematical Fix: You must consciously lower $d$. Realize that the "social cost" usually decays rapidly (people forget you said no within hours).

B. The Hidden Variable ($O$)

Most people ignore $O$ (Opportunity Cost). They calculate $P \cdot B - C$ and if it's positive, they say yes.

Correction: Even if the project is profitable ($P \cdot B > C$), if $O$ (the value of your focus time) is higher, the net utility is negative.

Rule: If you are "at capacity," $O$ approaches infinity. You mathematically cannot say yes to anything less than a life-changing opportunity.

C. The "Doormat" Derivative ($\frac{dRequests}{dYes}$)

In game theory, this is a repeated game.

If you say "Yes" to low-value tasks ($B$ is low), you signal that your $O$ (Opportunity Cost) is low.

This lowers your status in the hierarchy.

The Strategy: Saying "No" signals that your $O$ is high (i.e., "My time is valuable"). This can paradoxically increase your future $P \cdot B$ (people bring you better offers).

## Application: The "Say No" Algorithm

To make this practical, plug the request into this heuristic inequality.

Say NO if:

$$C_{real} + O > B_{adjusted} + \text{Guilt}$$

Where:

$C_{real}$ = $C \times 2$ (Always double your time estimate).

$O$ = What is the one major goal this prevents me from working on?

$B_{adjusted}$ = $P \times B$ (If the reward is vague "exposure" or "goodwill", $P$ is near 0).

Guilt = The temporary social friction ($d \cdot C_{nn}$).

The "High-Value No" Equilibrium:

Often, we fear $C_{nn}$ (being seen as not nice). However, if you provide a "High-Quality No" (polite, firm, no excuses), you reduce $C_{nn}$ to near zero.

$$\lim_{Politeness \to \infty} C_{nn} = 0$$

If $C_{nn} \approx 0$, the equation simplifies to: Is $P \cdot B > C + O$?

(Is the reward greater than the effort plus the opportunity cost?)

If not, the answer is No.

