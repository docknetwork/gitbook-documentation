# Slashing

The network can punish validators for being offline or equivocation in block production or finality. The nature and severity of the punishment also changes with the number of validators involved in the activity. If only 10% of validators are detected offline then no direct economic penalty \(slashing\) is applied. Otherwise, the penalty increases linearly to the number of offline validators. 

However, validators are removed from the current validator set and barred from participating in the next validator selection \(indirect economic penalty\) for being offline. This is called _chilling_. Validators found to be equivocating are sent to chilling and slashed, the slashing being quadratically proportional to the number of validators equivocating. Anticipating that a validator might go offline or might equivocate due to bugs in the software, the Council reserves the right to reverse any slashing event \(up to 6 epochs in the past, i.e. approx. 2 months\) by voting.

Reversing any slash requires at least a simple majority of Council votes. As the slashing amount increases, more Council votes are needed to reverse the slash.

