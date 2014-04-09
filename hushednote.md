## HushedNote - A note taking app that protects your privacy

I had been toying around this idea of secure end-to-end encrypted notes sharing app. This 
may not be of great importance to people like us but could be a life saving feature for journalists
and activists. Right now, any unencrypted data that is put on the internet is subject to scrutiny
and analysis. Although it has reached media significance only in the recent times in the context
of USA, there are multiple countries which are already doing it or planning to do it. 

I am not against a government, lawfully pursuing a person who might have committed a crime with proper
warrants. But, I am worried about the massive invasion of privacy by such blanket dragnets. The best
way to protect against it is to make sure that data that is stored on the cloud is opaque over the 
wire. HTTP/TLS is one option for transport but after that it is sitting in some server hosted by
companies whose primary revenue stream might be advertising backed by the contents that you put in the
notes. This is where the current models breakdown.

There are tools like GPG that will let you encrypt stuff and upload it to dropbox. But in practice it makes
it very difficult for average people to use it. That is why I propose to build this app that makes 
note taking as simple as EverNote but protects against blanket surveillance.

### MVP 1 - Note Taking:

The app itself will be an installed on the machine or the device. To start with, I am looking at a desktop
app. I use a Mac myself but many of the intended users use Windows/Linux. The initial version will atleast
run on a Mac/Linux. It will be able to store the notes written in Markdown and present it back as HTML. It
will also support identifying a local dropbox folder and writing the encrypted form of the documents to dropbox
for backup.

### MVP 2 - Collaboration (HushedNote Cloud)

To collaborate with other users, we will build a public key exchange a bit like keybase.io but only using email. The
user can associate a public key with an email address. We an verify the email address from the server end and once
verified, we can upload the user's public key to the key registry. When the user wants to share a note or notebook
with another user, we would check if we have the user's public key in the key registry, if not send an invite to the user
and once the public key becomes available encrypt and sign the note and upload it to S3. The S3 object will probably be a hash
of the note uuid on client. As and when the note changes, we will upload a new version of the note and make it available
to the other clients. Any patches or merges should happen on the client. Or we can have something like last version wins.

### V1 - Platforms

This is going to be the big one. We will have to expand to mobile as well. Each of the mobile apps will be native. We can target
iOS and Android. And this will then be ready for a press launch.
