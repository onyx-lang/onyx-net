# Onyx-Net

Stable and reliable networking protocol on top of UDP for
games and applications. It is based off of ENet, but is not compatible
in the slightest with it.

A single server is connected to by multiple clients using a UDP Socket
each. On each socket, multiple channels are used. Each channel supports:
    - Sequencing
    - Reliable transmissions
    - Commands (control codes)

These are supported independent of the other channels. This enable the
programmer to use sequencial packets for data that needs to arrive in
order, and unsequencial / unreliable packets for things like movement
updates.

This protocol will also support larger transmissions, though for
practically, assume that anything over 1MB in size should probably be
transferred in a different way, or chunked up by the application layer.


Currently, these features are not supported:
[ ] Bundle acknowledgement messages together.

[ ] Packets are not necessarily sequenced. A dropped packet followed
    by a successful packet with be out of order.

[x] Framemented reliable data.
