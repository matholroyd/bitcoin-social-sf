# Bitcoin social San Francisco
- 2012-06-28
- Location: StartupHQ

# Agenda:

- Introductions
  - Interest in bitcoin?
  - What are they working on?  
  
# Recap of recent events in the bitcoin world

- BitStamp.com doing 25% of MtGox's traffic/volume 
- Transactions jumped up significantly
  - Guessed due to satoshi dice
  - Maybe bitstamp
- New ASIC released by butterfly labs couple of weeks ago
  - People wondering about viability of them 
  - Questioning the reasons for the delivery delays
- Wallet apps that can send/receive bitcoins banned (again) in iOS app store
  - E.g. Blockchain.info 
- Facebook dropped credits, changing to payments in local currencies
  - Still take 30%? (still aimed at games)
- BitInstant
  - New locations all the time
  - In couple of weeks Eurozone will be "online" (?)
    - Ask Rodger
  - Credit card coming out that can top up with bitcoins
    - Hold balance in bitcoin or currency e.g. USD
- BitPay tripling every month
- New services
  - CoinBase
  - WeExchange.co  
  - BitFloor.com
- MtGox merchant thing coming
- Bitcoin Magazine
  - First issue out
- Bitcoinica 
  - Hacked (again)
  - Still down
- InfoDev.org released "Knowledge Map of the Virtual Economy"


# Other info

- Money transmit laws in US
  - They suck
  - California worst of states    
    
    
# People

I've setup a twitter list of the people I could find, who were at the bitcoin social meetup. 
https://twitter.com/#!/matholroyd/bitcoin-social-sf/members. Tweet me (@matholroyd) if I left you out.

- Mat Holroyd
  - Hosted this bitcoin social
  - BitPiggy.com
  - @matholroyd and @bitpiggy
- Andrew
  - btckink.com
- Jesse Powell
  - ogrr.com 
- Roger Ver
  - www.memorydealers.com 
  - http://bitcoinstore.com (not up yet)
  - http://www.bitcoinchipin.com
- Jed McCaleb
  - Started MtGox 
  - Currently working on secret project, some kind of better bitcoin
    - Fixes mining problem
- ?
  - http://lovebitcoins.org/
- Brian Armstrong
  - Coinbase.com
  

# Web security (Mat's talk that didn't happen):

## App
- Lock rows in table
  - Don't allow future changes
  - E.g. don't allow changing of bitcoin address, amounts, etc.
  - Don't allow deleting of rows
- Limits + checks 
  - Individual amounts
  - Total amounts e.g. per day
  - Check invalid row data at regular periods
  - Alarms + site lock down when bad data
  - Javascript only has one math type which is floats => imprecise!
- Use professional app hosting service
  - Heroku
  - Google app engine
  - Others
- SQL injection
  - Clean before perform calls
- Https only
  - Whole app, or else sessions can be stolen
  - Bitcoin addresses can me changed
  - Passwords can be observed
- Be careful of trusting 3rd-party login (e.g. via oauth)
 - Facebook trivial to hack, does not use https
 - LinkedIn recently hacked
- Password best practices
  - Better to allow long passwords versus enforce combinations of letters/symbols/etc
    - When forced to add numbers/symbols, majority of users put at end of password
  - Suggested
    - Salt for each user
    - Use sha512 or bcrypt
    - Require minimum of 12 characters, no maximum
  - Password reset via email is a security vulnerability
    - ~100% emails sent unencrypted
    - 2-layer authentication 
      - Perhaps only for high-risk features
      - SMS, google authenticator
- Guard against mass assignment
  - Ignore parameters you're not expecting 

## Wallet access
- Host wallet on separate server
  - Pre-generate or allow read-only access to server hosting wallet
  - Use 3rd-party service, e.g. BlockChain.info
    - But be careful of trusting 3rd-party apps. Get 2nd opinion if building a thin client
  - Host small amount of bitcoins locally which is topped up from time to time
- Don't store wallet access password in app/database
  - Require admin user to enter the actual password when making payments
  - Prevents automation though :(

## Source control
- Don't store API keys in source code
  - Make sure session info is not in source code
  - Cookie generating keys
  
## Database
- Encrypt database
  - Whole database or just fields in rows
- Encrypt client side
  - Blockchain.info 

## Developer machine
- Encrypt your harddrive!
- Backups
  - Encrypt backups
  - Delete old unencrypted backups
- Lock your machine when you're away from your desk
  - On Mac open up "Keychain Access" app, got preferences, turn on show in toolbar
  - Click lock icon to lock screen immediately 
- Use password managers
  - 1Password for Mac
  
## Build for a popular bitcoin conference. Assume
- Hackers on the same network as you and your users
- Hackers are physically near you
- You may forget your laptop, phone
- Your customers may lose their laptop, phone, leave it unlocked
