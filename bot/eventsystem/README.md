# YAGPDB's Event System

Instead of just using discordgo's standard simple event system, I like to experiment a little as I work on stuff to see what happens.

It all boils down to a simple 3D slice of handlers (handlers [][][]Handler)

The first index is the event index, that length is generated by events_gen.go

Next index is order, there is 3 orders:

0 - first ran
1 - state handler is here
2 - last, ran concurrently from here on

Orders 1 and 0 are run synchronously, but 2 is run concurrently, this is in order to have the state be as proper as possible.