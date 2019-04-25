---
title: Настройка службы проверки на соответствие для сервера сохраняемого чата в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: 'Сводка: Узнайте, как настроить службу соответствия Persistent Chat Server в Скайп для Business Server 2015.'
ms.openlocfilehash: 8364719f7d42b0627de579c7a0aa94c1e6370c45
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222082"
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Настройка службы проверки на соответствие для сервера сохраняемого чата в Skype для бизнеса Server 2015

**Сводка:** Узнайте, как настроить службу соответствия Persistent Chat Server в Скайп для Business Server 2015.

Проверка совместимости сохраняемого чата позволяет администраторам хранить архив сообщений сохраняемого чата и действий в нем. Служба соответствия записей и архивов данные, связанные с каждой беседы сервера сохраняемого чата, в том числе участника:

- Операторы комнаты сохраняемого чата

- покидает комнату чата;

- публикует сообщение;

- просматривает историю чата;

- отправляет файл;

- загружает файл.

Эта информация может извлекаться из базы данных проверки совместимости SQL по мере необходимости. 

> [!NOTE]
> Сохраняемый чат доступна в Скайп для Business Server 2015, но больше не поддерживается в Скайп для Business Server 2019. Те же функциональные возможности доступны в группах. Для получения дополнительных сведений см [Реализация из Скайп для бизнеса для групп Майкрософт](/microsoftteams/journey-skypeforbusiness-teams). Если необходимо использовать сохраняемого чата, возможны либо перенос пользователей, которым требуется эта функция групп, или для дальнейшего использования Скайп для Business Server 2015. 

## <a name="configure-the-compliance-service-by-using-windows-powershell"></a>Настройка службы проверки совместимости с помощью Windows PowerShell

Включив службы проверки совместимости с помощью построителя топологий, можно настроить ее путем выполнения командлета **Set-CsPersistenChatComplianceConfiguration**:

```
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

или

```
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

Можно задать следующие параметры.

- AdapterType - позволяет указать тип адаптера. Адаптер — это продукт сторонних производителей, который преобразует данные в базе данных соответствия требованиям в определенный формат. По умолчанию выполняется XML.

- OneChatRoomPerOutputFile — этот параметр позволяет указать, что, разделите отчеты должны быть созданы для каждой чат.

- AddChatRoomDetails - при включении этого параметра, этот параметр записывает Дополнительные сведения о каждом комнаты чата в базе данных. Поскольку этот параметр может существенно увеличить размер базы данных, он отключен по умолчанию.

- AddUserDetails - при включении этого параметра, этот параметр записывает Дополнительные сведения о каждом пользователе комнаты чата в базе данных. Поскольку этот параметр может существенно увеличить размер базы данных, он отключен по умолчанию.

- Удостоверение — этот параметр позволяет параметров соответствия требованиям для ограничения области для определенного семейства сайтов, включая глобальной, сайта и уровни обслуживания. Значение по умолчанию — глобальный уровень. 

- RunInterval. Этот параметр определяет длительность периода, по истечении которого на сервере создается новый выходной файл проверки совместимости (по умолчанию: 15 минут).

## <a name="use-a-customized-compliance-adapter"></a>Работа с пользовательским адаптером проверки совместимости

Можно написать пользовательский адаптер вместо использования адаптера xmladapter настраиваемым, который устанавливается вместе с сервера сохраняемого чата. Для этого необходимо предоставить сборку .NET Framework, которая содержит общий класс, реализующий интерфейс **IComplianceAdapter**. Эта сборка необходимо поместить в папку установки сервера сохраняемого чата каждого сервера в пуле серверов сохраняемого чата. Данные проверки совместимости могут поступать в адаптер с любого сервера проверки совместимости, но на разные экземпляры адаптера с серверов проверки совместимости на поступают повторяющиеся данные.

Интерфейс определен в сборке Compliance.dll в пространстве имен `Microsoft.Rtc.Internal.Chat.Server.Compliance`. Интерфейс определяет два метода, которые должен реализовать пользовательский адаптер.

Сервер соответствия Persistent Chat будет вызвать метод следующие при первой загрузке адаптера. `AdapterConfig` Содержит конфигурацию соответствия Persistent Chat, соответствующий адаптеру соответствия требованиям:

```
void SetConfig(AdapterConfig config)
```

Соответствия Persistent Chat server вызывает следующий метод через определенные интервалы, поскольку новые данные для перевода. Этот период равен `RunInterval` как задано в конфигурации соответствия Persistent Chat:

```
void Translate(ConversationCollection conversations)
```

`ConversationCollection` Содержит сведения о беседах, собранные с момента последнего последнем вызове этого метода.

## <a name="customize-the-xslt-definition-file"></a>Настройка файла определения XSLT

Данные проверки совместимости доставляются в формате XML, который можно с применением файла определения XSLT преобразовать в формат, подходящий для конкретной организации. Этот раздел содержит описание файла XML, созданного с помощью службы проверки совместимости. Приведены также примеры файла определения XSLT и выходного файла.

### <a name="output-format"></a>Форма выходных данных

Выходные данные службы проверки совместимости классифицируются по беседе (элемент Conversation) и затем по сообщению (элемент Messages), как показано в следующем примере кода:

```
<?xml version="1.0" encoding="utf-8" ?> 
<Conversations xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Conversation>
    <Channel uri="ma-chan://litwareinc.com/300" name="ma-chan://litwareinc.com/300" islogged="" /> 
    <!--FirstMessage goes here --!>
    <Messages> 
      <!—Messages go here--!>
    </Messages>
    <StartTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
    <EndTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
  </Conversation>
</Conversations>
```

Элемент Conversation содержит четыре элемента (Channel, FirstMessage, StartTimeUTC и EndTimeUTC). Элемент Channel содержит код URI, назначенный комнате чата, а элемент FirstMessage описывает первое сообщение в элементе Messages. Элементы StartTimeUTC и EndTimeUTC задают время начала и окончания беседы, как показано в следующем примере кода:

```
<<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

Элемент Message содержит два элемента (Sender и DateTimeUTC) и три атрибута (Type, Content и ID). Элемент Sender представляет пользователя, отправляющего сообщение, а элемент DateTimeUTC — время возникновения события, как показано в следующем примере кода:

```
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

В следующей таблице показаны атрибуты сообщений Type, Content и ID.

**Атрибуты элемента Messages**

|**Атрибут**|**Описание**|**Применение**|
|:-----|:-----|:-----|
|Тип  <br/> |Указывает тип сообщения. Типы сообщений описаны в таблице типов сообщений элемента Message.  <br/> |Обязательный  <br/> |
|Content  <br/> |Представляет собой содержимое сообщения. Для сообщений с типом Join или Part этот атрибут не используется.  <br/> |Необязательно   <br/> |
|ID  <br/> |Указывает уникальный идентификатор содержимого. Этот атрибут используется только с сообщениями, имеющими тип Chat.  <br/> |Необязательно   <br/> |

Каждый элемент Sender содержит пять атрибутов: имя пользователя, идентификатор, адрес электронной почты, принадлежность ко внутренним пользователям и URI-код. Эти атрибуты описаны в следующей таблице.

**Атрибуты элемента Sender**

|**Атрибут**|**Описание**|**Применение**|
|:-----|:-----|:-----|
|Username  <br/> |Имя отправителя.  <br/> |Необязательно   <br/> |
|ID  <br/> |Уникальный идентификатор отправителя.  <br/> |Обязательный  <br/> |
|Email  <br/> |Адрес электронной почты отправителя.  <br/> |Необязательно   <br/> |
|Internal  <br/> |Определяет, является ли пользователь внутренним или федеративным. Если задано значение true, пользователь является внутренним.  <br/> |Необязательный  <br/> |
|Uri  <br/> |URI SIP пользователя.  <br/> |Обязательно  <br/> |

В следующих примерах показано типы сообщений, которые может содержать элемент сообщения. Здесь также представлен пример использования каждого из элементов.

Соединение — пользователь присоединяется к комнате чата.

```
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

Часть — пользователь покидает комнату чата.

```
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

Чат - адрес электронной почты отправителя.

```
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

Ответ на чат - пользователь запрашивает содержимое из истории чата.

```
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

Отправка файла - пользователь отправляет файл.

```
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

Загрузка файла — пользователь загружает файл.

```
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a>По умолчанию выходные данные сохраняемого чата XSD и пример преобразования XSL

Следующий пример кода содержит выходные данные сервера проверки совместимости по умолчанию:

```
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="Conversations" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">
   <xs:simpleType name="ComplianceMessageType">
      <xs:restriction base="xs:string">
        <xs:enumeration value="JOIN"/>
        <xs:enumeration value="PART"/>
        <xs:enumeration value="CHAT"/>
        <xs:enumeration value="BACKCHAT"/>
        <xs:enumeration value="FILEUPLOAD"/>
        <xs:enumeration value="FILEDOWNLOAD"/>
      </xs:restriction>
    </xs:simpleType>

  <xs:element name="Sender">
    <xs:complexType>
      <xs:attribute name="UserName" type="xs:string" />
      <xs:attribute name="id" type="xs:int" />
      <xs:attribute name="email" type="xs:string" use="optional" />
      <xs:attribute name="internal" type="xs:boolean" use="optional" >
        <xs:annotation><xs:documentation>If the user is internal or federated</xs:documentation></xs:annotation>
      </xs:attribute>
      <xs:attribute name="uri" type="xs:anyURI" use="optional" />
    </xs:complexType>
  </xs:element>
  <xs:element name="DateTimeUTC">
    <xs:complexType>
      <xs:attribute name="since1970" type="xs:long" />
      <xs:attribute name="string" type="xs:string" />
      <xs:attribute name="long" type="xs:long" />
    </xs:complexType>
  </xs:element>
  <xs:element name="Conversations" msdata:IsDataSet="true" msdata:UseCurrentLocale="true">
    <xs:complexType>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element ref="Sender" />
        <xs:element ref="DateTimeUTC" />
        <xs:element name="Conversation">
          <xs:complexType>
            <xs:sequence>
              <xs:element name="Channel" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="uri" type="xs:anyURI" />
                  <xs:attribute name="name" type="xs:string" use="optional" />
                </xs:complexType>
              </xs:element>
              <xs:element name="FirstMessage" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                    <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                  </xs:sequence>
                  <xs:attribute name="type" type="ComplianceMessageType" />
                  <xs:attribute name="content" type="xs:string" />
                  <xs:attribute name="id" type="xs:int" />
                </xs:complexType>
              </xs:element>
              <xs:element name="Messages" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element name="Message" minOccurs="0" maxOccurs="unbounded">
                      <xs:complexType>
                        <xs:sequence>
                          <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                          <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                        </xs:sequence>
                        <xs:attribute name="type" type="ComplianceMessageType" />
                        <xs:attribute name="content" type="xs:string" />
                        <xs:attribute name="id" type="xs:int" />
                      </xs:complexType>
                    </xs:element>
                  </xs:sequence>
                </xs:complexType>
              </xs:element>
              <xs:element name="StartTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
              <xs:element name="EndTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
            </xs:sequence>
          </xs:complexType>
        </xs:element>
      </xs:choice>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

Следующий образец кода содержит пример преобразования в формат XSL:

```
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" exclude-result-prefixes="xs">
   <xsl:output method="xml" encoding="UTF-8" indent="yes" />

   <xsl:template match="/">
      <FileDump>
         <xsl:apply-templates />
      </FileDump>
   </xsl:template>

   <xsl:template match="Conversation">
      <xsl:variable name="chanName" select="Channel/@name" />
      <Conversation Perspective="{$chanName}_group_channel">
         <RoomID><xsl:value-of select="Channel/@name" /></RoomID>
         <StartTimeUTC><xsl:value-of select="StartTimeUTC/@since1970" /></StartTimeUTC>
         <xsl:apply-templates />
         <EndTimeUTC><xsl:value-of select="EndTimeUTC/@since1970" /></EndTimeUTC>
      </Conversation>
   </xsl:template>

   <xsl:template match="Message">
      <xsl:choose>
         <xsl:when test="@type='JOIN'">
            <ParticipantEntered>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantEntered>
         </xsl:when>

         <xsl:when test="@type='PART'">
            <ParticipantLeft>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantLeft>
         </xsl:when>

         <xsl:when test="@type='FILEUPLOAD' or @type='FILEDOWNLOAD'">
            <FileTransferStarted>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
            </FileTransferStarted>
            <FileTransferEnded>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
               <Status>Completed</Status>
            </FileTransferEnded>
         </xsl:when>

         <xsl:when test="@type='CHAT' or @type='BACKCHAT'">
            <Message>
               <xsl:call-template name="DateTimeAndLogin" />
               <Content><xsl:value-of select="@content" /></Content>
            </Message>
         </xsl:when>

         <xsl:otherwise />
      </xsl:choose>
   </xsl:template>

   <xsl:template name="DateTimeAndLogin">
      <LoginName><xsl:value-of select="Sender/@userName" /></LoginName>
      <DateTimeUTC><xsl:value-of select="DateTimeUTC/@since1970" /></DateTimeUTC>
   </xsl:template>
</xsl:stylesheet>
```
