# Greeting
- Hi
- Hello
- Good morning
- Good evening

# Help
- help
- I need help
- please help

# AskForUserName
- {userName=vishwac}
- I'm {userName=vishwac}
- call me {userName=vishwac}
- my name is {userName=vishwac}
- {userName=vishwac} is my name
- you can call me {userName=vishwac}

> # Entity definitions
$userName:simple

> PREBUILT entities are global. LUIS will always provide results for these when ever a prebuilt entity is found in any utterance.

$PREBUILT:datetimeV2

# CreateAlarm
- create an alarm
- create an alarm for 7AM 
- set an alarm for 7AM next thursday

> add these as patterns

# DeleteAlarm
> this utterance will be added as a pattern since there is no labelled value for the alarmTime entity

- delete the {alarmTime} alarm 
- remove the {alarmTime} alarm 

> Since there is a list entity definition, any synonyms in this list will get picked up as list entity type and should not be labelled
# CommunicationPreference
- set phone call as my communication preference
- I prefer to receive text message

> List entity definition 

$commPreference:call=
- phone call
- give me a ring
- ring
- call
- cell phone
- phone

# Help
- can you help

> you can break up list entity definitions into multiple chunks, interleaved within a .lu file or even spread across .lu files.

$commPreference:text=
- message
- text
- sms
- text message

$commPreference:fax=
- fax
- fascimile

> You can have references to external .lu files

[None intent definition](./none.lu)

[Buy chocolate definition](./buyChocolate.lu)

> Qna pairs

### ? How can I change the default message from QnA Maker?
```
You can change the default message if you use the QnAMakerDialog. See this for details: https://docs.botframework.com/en-us/azure-bot-service/templates/qnamaker/#navtitle
```

### ? How do I programmatically update my KB?
```
You can use our REST apis to manage your KB. See here for details: https://westus.dev.cognitive.microsoft.com/docs/services/58994a073d9e04097c7ba6fe/operations/58994a073d9e041ad42d9baa
```

### ? Who is your ceo?
- get me your ceo info
```markdown
Vishwac Sena Kannan
```

> FAQ URLs for QnA maker to ingest.

[QnA maker reference](https://docs.microsoft.com/en-in/azure/cognitive-services/qnamaker/faqs)
