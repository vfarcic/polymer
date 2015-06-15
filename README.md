Dependencies
============

```sh
npm install -g gulp bower
npm install
bower install
```

Run
===

```bash
sudo docker run -d --name oauth \
	-p 8081:8080 \
	-v /etc/ssl/certs:/etc/ssl/certs \
	-v /data/oauth:/data/db \
	-e PORT=8081 \
	-e SEC_KEY="Bla" \
	-e REDIRECT_URL="http://localhost:3000" \
	-e GOOGLE_CLIENT_ID="472858977716-ej3ca5dtmq4krl7m085rpfno3cjp2ogp.apps.googleusercontent.com" \
	-e GOOGLE_SECRET="OnkptU4BTdE45mi-b3hACdAY" \
	-e GOOGLE_REDIRECT_URL="http://localhost:8081/auth/google/callback" \
	vfarcic/oauth
	
sudo docker run -d --name chat \
	-p 8082:8080 \
	-v /etc/ssl/certs:/etc/ssl/certs \
	-e PORT=8082 \
	vfarcic/chat

gulp serve
```

This outputs an IP address you can use to locally test and another that can be used on devices connected to your network.

TODO
====

Fix API calls when not logged in.
Tests
Reconnecting in XXX seconds
