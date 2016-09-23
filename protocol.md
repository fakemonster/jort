# The JORT Protocol
Protocol for a simple p2p chat system

## Connection

When a client comes online it should do the two following things:
	1. Ping the local network to see if peers exist
	2. Establish a listener to respond to future 
	
## Heartbeat

On discovery, the discovered user should initiate a heartbeat.
If the heartbeat initializer does not receive a heartbeat response
within 3 seconds of sending a heartbeat message, the connection
should be dropped. Likewise, if the heartbeat recipient fails to receive
a heartbeat message within 3 seconds of the last heartbeat response,
the connection should be dropped.

## Communication

Communication messages can be directed at the group, or at subsets
of users in the in the group. Such routing should be handled by each
client. Messages should only include the username of the source and
and the content of the message.

## Leaving

When a user leaves, they should broadcast that to the group in a _/leave_
message and recipients of that message should remove the user from their lists
of users.
	
## Commands

- /ping
-- Username
-- IP Address

- /pong
-- Username
-- IP Adress

- /heartbeat-start
- /heartbeat-end

- /message
-- username
-- body content

- /leave
-- Username

## Things to consider

- How to restart ceased communications??? Just a "ping" button??
- How to handle mutiple instances of the same username?

