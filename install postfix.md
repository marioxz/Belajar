# Install Postfix

sudo apt-get update
sudo DEBIAN_PRIORITY=low apt-get install postfix

Use the following information to fill in your prompts correctly for your environment:
->  General type of mail configuration?: For this, we will choose Internet Site since this matches our infrastructure needs.
    System mail name: This is the base domain used to construct a valid email address when only the account portion of the address is given. For instance, the hostname of our server is mail.example.com, but we probably want to set the system mail name to example.com so that given the username user1, Postfix will use the address user1@example.com.
    Root and postmaster mail recipient: This is the Linux account that will be forwarded mail addressed to root@ and postmaster@. Use your primary account for this. In our case, sammy.
    Other destinations to accept mail for: This defines the mail destinations that this Postfix instance will accept. If you need to add any other domains that this server will be responsible for receiving, add those here, otherwise, the default should work fine.
    Force synchronous updates on mail queue?: Since you are likely using a journaled filesystem, accept No here.
    Local networks: This is a list of the networks that your mail server is configured to relay messages for. The default should work for most scenarios. If you choose to modify it, make sure to be very restrictive in regards to the network range.
    Mailbox size limit: This can be used to limit the size of messages. Setting it to "0" disables any size restriction.
    Local address extension character: This is the character that can be used to separate the regular portion of the address from an extension (used to create dynamic aliases).
    Internet protocols to use: Choose whether to restrict the IP version that Postfix supports. We'll pick "all" for our purposes.
