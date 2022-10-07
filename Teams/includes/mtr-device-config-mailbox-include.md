
Вы можете улучшить Комнаты Teams собрания, настроив способ ответа учетной записи ресурса и процессы, приглашения на собрания. С Exchange Online PowerShell можно задать следующие свойства учетной записи ресурса:

- **AutomateProcessing: `AutoAccept`** Организаторы собраний получают решение о резервировании помещений напрямую без вмешательства человека.

- **AddOrganizerToSubject: `$false`** Организатор собрания не добавляется в тему приглашения на собрание.

- **DeleteComments: `$false`** Сохраните любой текст в тексте сообщения о входящих приглашениях на собрания. Это необходимо для обработки внешних собраний Teams и сторонних разработчиков, чтобы обеспечить взаимодействие с One Touch Join.

- **DeleteSubject: `$false`** Оставьте тему входящих приглашений на собрание.

- **ProcessExternalMeetingMessages: `$true`** Указывает, следует ли обрабатывать приглашения на собрания, поступающие за пределы организации Exchange. Требуется для внешних собраний Teams и [сторонних собраний](/microsoftteams/rooms/third-party-join).

- **RemovePrivateProperty: `$false`** Гарантирует, что закрытый флаг, отправленный организатором собрания в исходном приглашении на собрание, остается указанным.

- **AddAdditionalResponse: `$true`** Текст, указанный параметром AdditionalResponse, добавляется в приглашения на собрания.

- **AdditionalResponse: "Это комната для собраний Microsoft Teams!"** Дополнительный текст, добавляемый в ответ на принятие собрания.

Чтобы настроить эти свойства, необходимо подключиться к Exchange Online PowerShell. Дополнительные сведения см. в [разделе "Подключение Exchange Online PowerShell"](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true).

После подключения к Exchange Online PowerShell можно настроить свойства почтового ящика в учетной записи ресурса с помощью [командлета Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

В следующем примере задается свойство учетной записи `ConferenceRoom01` ресурса:

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

