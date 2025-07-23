## Disclamer
This project is modified version of [Flutter SMS Inbox](https://github.com/jgithaiga/flutter_sms_inbox) for filter by date.

# Flutter SMS Inbox with Filter

Flutter android SMS inbox library based on [Flutter SMS](https://github.com/babariviere/flutter_sms).

### Dependencies

This package in turn uses the permission handler package for permission handling, [Permission Handler](https://pub.dev/packages/permission_handler).

You need to add it to your project:

```
dependencies:
  permission_handler: ^10.2.0
```

## Querying SMS messages

Add the import statement for sms and create an instance of the SmsQuery class:

```
import 'package:flutter_sms_inbox/flutter_sms_inbox.dart';

void main() {
  SmsQuery query = SmsQuery();
}
```

## Getting all SMS messages

`List<SmsMessage> messages = await query.getAllSms;`

## Filtering SMS messages
The method `querySms` from the `SmsQuery` class returns a list of sms depending of the supplied parameters. For example, for querying all the sms messages sent and received write the followed code:

```
await query.querySms(
    kinds: [SmsQueryKind.inbox, SmsQueryKind.sent],
    startTime: DateTime.now().subtract(Duration(days: 1)),
    endTime: DateTime.now(),
);
```
You can also query all the sms messages sent and received from a specific contact:

```
await query.querySms(
    address: getContactAddress()
);
```
