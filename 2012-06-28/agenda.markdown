# Agenda:

- Introductions
  - Interest in bitcoin?
  - What are they working on?
- Recap of recent events in the bitcoin world
  - New ASIC released by butterfly labs couple of weeks ago
  - Wallet apps that can send/receive bitcoins banned (again) in iOS app store
    - Blockchain.info 
  - InfoDev.org released "Knowledge Map of the Virtual Economy"
  - New services
    - CoinBase
- Speakers
  - Mat - web + personal security
  - Other guy
  - Mat - BPS
  - Others?
- Social
  - Go somewhere nearby for beer

# Web security:

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
