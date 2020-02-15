The following algorithm is one-note and might require much more building for multiplatform inclusion.

tl;dr: Contributions welcome :)

```
Counter exceeded ->
	Sleep (`n` time)
	Restart
WiFi Found ->
	Connected ->
		Connected to different Wifi ->
			WiFi in whitelist ->
				Sleep (Listen for disconnection)
				Restart
			WiFi in blacklist ->
				Force disconnect
				Restart
			WiFi not mentioned ->
				Ping success ->
					Sleep (Listen for disconnection)
					Restart
				Ping failed ->
					Prompt to keep connected
					Sleep (`m` time)
					Prompt replied ->
						Sleep (Listen for disconnection)
						Restart
					Prompt ignored ->
						Force disconnect
						Restart
		Connected to network ->
			Not Logged In ->
			Try login
			Logged In ->
			Try connection
	Not Connected ->
		Connect to network
			Unsuccessful ->
				Increment timeout counter
			Jump to START
ION Not Found ->
	Sleep (`n` time)
	Restart
```
