---
categories: General discussions
title: Neural basis of perceptual decision
---

# Perceptual decision

Deciding where to turn to avoid an object while you drive.
Telling which direction something's travelling. Judging
whether a lane is faster than another. All these acts that
we continuously perform every day of our lives involve
taking a decision based on the analysis of the behavior
of the world around us. This is called a perceptual decision.

A perceptual decision is the act of executing an action on
the basis of your perception. This involves the extraction
of a relevant signal from your senses, its integration, and the
forming of a decision. But how can this happen inside our brains? One possible answer was given by Wang in 2002 with his "winner-takes-all" network.

![winner-takes-all]({{/assets/wta_net_desc.png | absolute_url}})

The winner-takes-all network is a Recurrent Neural Network
where two recurrent excitatory populations compete with each
other via a population of inhibitory interneurons. The signal
encoding the relevant quantity perceived (e.g. a signal coding
  the speed of motion of an object in a given direction) is fed
  to the corresponding network. This causes an increase in its
  activity, which in turn increases the activity of the inhibitory interneurons until one of the two populations
  reaches a level of activity high enough to sustain itself. At this point the interneurons drive the "losing" population down and a decision is made. The dynamics then reaches a stable point, known as "Attractor"

This behavior is best understood if one makes use of a conceptual simplification known as the energy landscape. Similarly to what happens with physical systems, we can define an energy function whose values, plotted in the phase space of the system, will give rise to the energy landscape. We can envision our system as a small ball on this landscape, which will run along a slope until it reaches the end of a hole (if there is one) and is trapped there.

![energy landscape]({{/assets/landscape.png | absolute_url}})

The picture above depicts a representation of the energy landscape for our winner-takes-all network with different imbalances between the inputs (the "coh" parameter); when no stimulus is present, the network stays in the central region, in an attractor at low frequency for both A and B. When external stimulation is applied though, a decision boundary is formed and the landscape takes the form of a saddle. The system, driven by noise, begins to drift around it until it is too far in one of the valleys and falls in one of the attractors. The difference between the two inputs determines which attraction basin (the set of states from which you will fall into an attractor) is bigger, and thus which will be the most probable outcome. The model reproduces data previously gathered during a random dots experiment.

This shows how even a simple and small network is capable to take a decision based on signals coming from perceptual systems even when this decision is hard or next to impossible (or even ill-posed, as when the two signals are equal) thanks to the contribution of noise. This simple network has been extensively used both in simulations and in its VLSI implementation, and in following posts I will detail how these perceptual signals might be extracted in the case of the visual system, and how these networks can be implemented on low-power hardware performing analog computation (a.k.a. neuromorphic hardware).
