
# models

## user

- id = is unique id, autoincrement in the situation this lives in (the crystal twin)
- tfid = 3botconnect id (will be called ThreeFold ID in future)
- name = optional name 
- email = 3bot connect email
- mobile
- registration_date
- list(referral)
- list(action)

## action

- id
- date (epoch)
- category (dot notation based e.g. user.registration, user.referral)
- data: anything relevant for that action
- comment: optional
- list(log)
- state (ERROR, OK)

## referral

- id
- category (dot notation based e.g. threefold.user or crystaltwin.promo.forlife). us used to identity the type of referral
- name: as used by the person to refer to a person
- email: email used to refer a person
- referral: is a unique code which can be used for remote person to login and accept the referral
- referral_user_id : person which got referred, optional, empty as long as user did not log in
- message, can be customized by user, otherwise is template based
- list(tasklet_str) is string which points to position of tasklet

e.g. template could be

```
Dear #{name}

I just came accross this amazing new internet project called ThreeFold.
ThreeFold is building a new internet where our data is free.

...

```

## log

- id
- message
- date (epoch)
- category
- 
- data

