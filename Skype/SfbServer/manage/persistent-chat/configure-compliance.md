---
title: Настройка службы соответствия для сервера сохраняемой беседы в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: Сводка. Сведения о настройке службы соответствия сервера сохраняемой беседы в Skype для бизнеса Server 2015.
ms.openlocfilehash: ee7dbc3ad8e7eedcadcc60850e35b753c5fadb43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815069"
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Настройка службы соответствия для сервера сохраняемой беседы в Skype для бизнеса Server 2015

**Сводка:** Узнайте, как настроить службу соответствия для сервера сохраняемой беседы в Skype для бизнеса Server 2015.

Соответствие сохраняемого чата позволяет администраторам поддерживать архив сообщений сохраняемого чата, а также действий. Служба соответствия требованиям записи и архивы данных, связанных с каждой беседой сервера сохраняемого чата, в том числе, когда участник:

- Присоединяется к комнате сохраняемой беседы

- покидает комнату чата;

- публикует сообщение;

- просматривает историю чата;

- отправляет файл;

- загружает файл.

Эти сведения можно получить из базы данных SQL соответствия требованиям при необходимости. 

> [!NOTE]
> Сохраняемая беседа доступна в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019. Такие же функции доступны в Teams. Дополнительные сведения [см. в сведениях о том,](/microsoftteams/upgrade-start-here)как начать обновление Microsoft Teams. Если необходимо использовать сохраняемого чата, вы можете либо перенести пользователей, которым требуются эти функции, в Teams, либо продолжить использование Skype для бизнеса Server 2015. 

## <a name="configure-the-compliance-service-by-using-windows-powershell"></a>Настройка службы соответствия с помощью Windows PowerShell

После включения службы соответствия с помощью построитель топологий ее можно настроить с помощью cmdlet **Set-CsPersistenChatComplianceConfiguration:**

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

или

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

Можно установить следующие параметры:

- AdapterType — позволяет указать тип адаптеров. Адаптер — это сторонний продукт, который преобразует данные в базе данных соответствия в определенный формат. XML по умолчанию.

- OneChatRoomPerOutputFile — этот параметр позволяет указать отдельные отчеты, которые необходимо создать для каждой комнаты чата.

- AddChatRoomDetails . Если этот параметр включен, этот параметр записи дополнительные сведения о каждой комнате чата в базе данных. Поскольку этот параметр может значительно увеличить размер базы данных, он по умолчанию отключен.

- AddUserDetails . Если этот параметр включен, этот параметр записи дополнительные сведения о каждом пользователе комнаты чата в базе данных. Поскольку этот параметр может значительно увеличить размер базы данных, он по умолчанию отключен.

- Identity — этот параметр позволяет настраивать параметры соответствия для определенной коллекции, включая глобальные уровни, уровни сайтов и служб. Значение по умолчанию — глобальный уровень. 

- RunInterval — этот параметр определяет время, в течение времени до создания сервером следующего выходного файла соответствия требованиям (значение по умолчанию — 15 минут).

## <a name="use-a-customized-compliance-adapter"></a>Использование настроенного адаптера соответствия требованиям

Можно написать пользовательский адаптер вместо XmlAdapter, установленного с сервером сохраняемого чата. Для этого необходимо предоставить сборку .NET Framework, содержащую общий класс, который реализует интерфейс **IComplianceAdapter**. Эту сборку необходимо разместить в папке установки сервера сохраняемого чата каждого сервера в пуле серверов сохраняемого чата. Любой из серверов совместимости может предоставлять данные о совместимости адаптеру, но серверы совместимости не могут предоставлять дублированные данные о совместимости нескольким экземплярам адаптера.

Интерфейс определяется в сборке Compliance.dll в пространстве  `Microsoft.Rtc.Internal.Chat.Server.Compliance` имен. В интерфейсе определены два метода, которые должен реализовать настраиваемый адаптер.

Сервер соответствия сохраняемого чата будет вызывать следующий метод при первой загрузке адаптер. Содержит  `AdapterConfig` конфигурацию соответствия сохраняемой беседы, соответствующую адаптеру соответствия:

```cpp
void SetConfig(AdapterConfig config)
```

Сервер соответствия сохраняемого чата периодически вызывает следующий метод, если имеются новые данные для перевода. Этот интервал времени равен установленного в конфигурации соответствия  `RunInterval` сохраняемой беседы:

```cpp
void Translate(ConversationCollection conversations)
```

Содержит  `ConversationCollection` сведения о беседе, собранные с последнего метода.

## <a name="customize-the-xslt-definition-file"></a>Настройка файла определения XSLT

Данные соответствия доставляются в формате XML, который можно преобразовать в формат, который лучше всего подходит для вашей организации, с помощью XSLT-файла определения. В этом разделе описывается XML-файл, который создает служба соответствия требованиям. Он также предоставляет примеры XSLT-файлов определений и выходных файлов.

### <a name="output-format"></a>Формат выходных данных

Выходные данные службы соответствия классифицируются по беседе (элемент Conversation), а затем по сообщению (элемент Messages), как показано в следующем примере кода:

```XML
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

Элемент Conversation содержит четыре элемента (Channel, FirstMessage, StartTimeUTC и EndTimeUTC). Элемент Channel содержит URI-код комнаты чата, а элемент FirstMessage описывает первое сообщение в элементе Messages. Элементы StartTimeUTC и EndTimeUTC предоставляют время начала и окончания беседы, как показано в следующем примере кода:

```xml
<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

Элемент Message содержит два элемента (Sender и DateTimeUTC) и три атрибута (Type, Content и ID). Элемент Sender представляет пользователя, отправившего сообщение, а элемент DateTimeUTC — время возникновения события, как показано в следующем примере кода:

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

В следующей таблице показаны атрибуты сообщений Type, Content и ID.

**Атрибуты элемента Messages**

|**Атрибут**|**Описание**|**Необязательный/необходимый**|
|:-----|:-----|:-----|
|Тип  <br/> |Указывает тип сообщения. Типы сообщений описаны в таблице типов сообщений элемента Message.  <br/> |Обязательна  <br/> |
|Контент  <br/> |Представляет собой содержимое сообщения. Для сообщений с типом Join или Part этот атрибут не используется.  <br/> |Необязательна  <br/> |
|ID  <br/> |Указывает уникальный идентификатор содержимого. Этот атрибут используется только с сообщениями, имеющими тип Chat.  <br/> |Необязательна  <br/> |

Каждый элемент Sender содержит пять атрибутов: имя пользователя, идентификатор, адрес электронной почты, принадлежность ко внутренним пользователям и URI-код. Эти атрибуты описаны в следующей таблице.

**Атрибуты элемента Sender**

|**Атрибут**|**Описание**|**Необязательный/необходимый**|
|:-----|:-----|:-----|
|Имя пользователя  <br/> |Имя отправителя.  <br/> |Необязательна  <br/> |
|ID  <br/> |Уникальный ИД отправитель.  <br/> |Обязательна  <br/> |
|Электронная почта  <br/> |Электронный адрес отправителя.  <br/> |Необязательна  <br/> |
|Внутренний  <br/> |Определяет, является ли пользователь внутренним или федеративным. Если задано значение true, пользователь является внутренним.  <br/> |Необязательна  <br/> |
|Uri  <br/> |URI SIP пользователя.  <br/> |Обязательна  <br/> |

В следующих примерах покажите типы сообщений, которые может содержать элемент Messages. Здесь также представлен пример использования каждого из элементов.

Join — пользователь присоединяется к комнате чата.

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

Часть — пользователь покидает комнату чата.

```xml
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

Чат — адрес электронной почты отправитель.

```xml
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

Backchat — пользователь запрашивает содержимое из истории чата.

```xml
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

Отправка файла — пользователь загружает файл.

```xml
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

Загрузка файла— пользователь скачивает файл.

```xml
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a>XSD-данные сохраняемой беседы по умолчанию и пример преобразования XSL

Следующий пример кода содержит выходные данные по умолчанию с сервера соответствия требованиям:

```xml
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

В следующем примере кода содержится пример преобразования XSL:

```xml
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
