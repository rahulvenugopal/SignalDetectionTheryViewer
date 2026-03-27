#### At its core, the framework behind Signal Detection Theory (SDT) is a formal mathematical model of decision-making under uncertainty.

It was originally developed during World War II by radar engineers who needed to figure out how to tune their equipment (and train their operators) 
to detect enemy bombers ("signals") without being overwhelmed by flocks of birds or weather patterns ("noise"). 
Psychologists later realized this perfectly describes how the human nervous system works.

#### Every SDT analysis begins with the environment. The framework assumes there are only two possible states of the world (Signal Present or Signal Absent) and two possible actions by the observer ("Yes" or "No").

This creates the classic 2x2 contingency table (often called a confusion matrix):

    Hit: Signal present, response "Yes".

    Miss: Signal present, response "No".

    False Alarm (FA): Signal absent, response "Yes".

    Correct Rejection (CR): Signal absent, response "No".

The framework dictates that the probabilities in the columns must sum to 1. Therefore, you only actually need two numbers to understand the entire observable system: the Hit Rate and the False Alarm Rate.

#### The Latent Architecture: The Internal Response Axis

The framework assumes that the observer cannot directly perceive the "truth" of the world. Instead, they only have access to an internal sensory or cognitive variable—let's call it x (e.g., the brightness of a blip on a screen, or the feeling of familiarity of a memory).

Because the nervous system is inherently noisy, the value of x fluctuates wildly. This is why the framework models reality as two overlapping probability density functions (the bell curves):

    f(x∣N): The probability of experiencing evidence level x given only Noise.

    f(x∣S): The probability of experiencing evidence level x given a Signal plus Noise.

In SDT, we assume that "Internal Evidence" (how loud the sound is, how familiar the word feels) follows a normal distribution (a bell curve).

    The X-axis is the strength of the evidence (a continuous distance).

    The Area under the curve represents the probability of a response (a percentage, like your Hit Rate or False Alarm Rate).

We cannot look inside a participant's brain to measure the exact X-axis distance between their "Noise" and "Signal" curves. All we have is their behavioral data: the percentage of times they said "Yes" (the area under the curve).

The Z-score is the mathematical translator. It acts as the inverse cumulative distribution function. When you plug a percentage (like an 80% Hit Rate) into a Z-table, the Z-score tells you exactly where that vertical threshold line sits on the X-axis of a standard bell curve.

By Z-scoring both the Hit Rate and the False Alarm Rate, we translate two unlinked percentages into two concrete coordinates on the same internal mental axis. Once we have those coordinates, we can measure the distance between them.
2. The Non-Linearity Problem (Why Simple Math Fails)

You might wonder: Why go through the trouble of Z-scoring? Why not just measure sensitivity by subtracting the False Alarm Rate from the Hit Rate (Hit%−FA%)?

We cannot do that because percentages are bounded (0 to 100), but standard normal distributions are unbounded and curved. Because of the shape of a bell curve, most of the data is clustered in the fat middle, and very little data is in the thin tails. This means an equal jump in percentage requires vastly different amounts of cognitive "effort" depending on where you are on the curve.

Consider two scenarios where a participant improves their Hit Rate by exactly 5%:

    Scenario A (The Middle): Improving Hit Rate from 50% to 55%. Because the middle of the bell curve is fat, it takes only a tiny shift in internal evidence to cover 5% of the area. The Z-score changes from 0 to 0.12 (a very small increase in d′).

    Scenario B (The Extremes): Improving Hit Rate from 90% to 95%. Because the tail of the bell curve is extremely thin, you have to push the threshold drastically far down the X-axis to capture that extra 5% of area. The Z-score changes from 1.28 to 1.64 (a massive increase in d′).

If we just subtracted percentages, Scenario A and Scenario B would look like the exact same improvement (+5%). By converting to Z-scores, SDT correctly reveals that Scenario B requires a much stronger signal detection ability.
3. Calculating d′ and c with Z-Scores

Once the probabilities are converted into Z-scores (standard deviations from the center), the formulas for SDT become simple geometry on a 1D line.

    Sensitivity (d′): This is just the total distance between the Signal distribution and the Noise distribution.
    d′=Z(HitRate)−Z(FalseAlarmRate)

    Criterion (c): This measures how far the participant's threshold is from the neutral zero point (the exact intersection of the two curves).
    c=−2Z(HitRate)+Z(FalseAlarmRate)​

(Note: If a participant has a 100% Hit Rate or 0% False Alarm Rate, the Z-score is technically infinity because the tails of a normal curve never touch zero. In practice, researchers have to apply a slight mathematical correction—like changing 100% to 99%—to make the Z-score calculable).
