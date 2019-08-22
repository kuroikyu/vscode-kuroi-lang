# Kuroi format spec
VSCode language Support for .kuroi files

## Headers
Headers will be surrounded by square brackets. They contain the date of the entry using the following format: `[YYY-MM-DD ddd hh:mm]`.

### Date
This is the only mandatory part of the header. The format must match `YYYY-MM-DD`. E.g.: 2019-12-31

### Day of the week
Optional. Must use only 3 characters `ddd`. Available. E.g. Tue for Tuesday.

### Time
Optional. The format must match `hh:mm`. Uses 24h format. E.g.: 18:54 for 6:54PM.

```
[2019-01-01]
  Entry text...

[2019-03-17 Sun]
  Some text...

[2019-05-29 Wed 17:22]
  Entry starts here...
```

## Body
The body will be defined by indenting text after a header. The indentation will be a single tab character, by default of 4 spaces.

```
[2019-01-01]
  This is the body of the entry. Here's where tags and mentions (see below) can be added. It can be many lines long and it supports any kind of syntax in it like:
    - Lists
    2. Numbered lists
      - More indentation
  It won't stop being part of the entry until another date header is found so feel free to do type whatever you want here.
```

## Mentions and tags
Mentions and tags are words with no whitespace between them and are identified by their starting character, `@` for mentions and `#` for tags. E.g.: @Tom, #work, @SusanSmith, #camera_equipment

```
[2019-11-23]
  I received a gift from @Jane for my #birthday. I was happy to find that @Claire and @John have a puppy now.
```

## TODO and DONE
`TODO` and `DONE` are keywords that can be used to create and track checklists. Both have a lenth of 4 characters so it's really easy to keep everyting in line as long as you're using a monospaced font.

```
[2019-12-10]
  Checklist for the holiday season
  DONE Find a venue
  DONE Make a reservation
  TODO Buy a new tie
  TODO Iron shirt
  TODO Have fun!
```
