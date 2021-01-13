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
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="57fe2-103">Настройка службы соответствия для сервера сохраняемой беседы в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="57fe2-103">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>

<span data-ttu-id="57fe2-104">**Сводка:** Узнайте, как настроить службу соответствия для сервера сохраняемой беседы в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="57fe2-104">**Summary:** Learn how to configure the Persistent Chat Server Compliance service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="57fe2-105">Соответствие сохраняемого чата позволяет администраторам поддерживать архив сообщений сохраняемого чата, а также действий.</span><span class="sxs-lookup"><span data-stu-id="57fe2-105">Persistent Chat compliance lets administrators maintain an archive of Persistent Chat messages as well as activities.</span></span> <span data-ttu-id="57fe2-106">Служба соответствия требованиям записи и архивы данных, связанных с каждой беседой сервера сохраняемого чата, в том числе, когда участник:</span><span class="sxs-lookup"><span data-stu-id="57fe2-106">The Compliance service records and archives data related to each Persistent Chat Server conversation, including when a participant:</span></span>

- <span data-ttu-id="57fe2-107">Присоединяется к комнате сохраняемой беседы</span><span class="sxs-lookup"><span data-stu-id="57fe2-107">Joins a Persistent Chat room</span></span>

- <span data-ttu-id="57fe2-108">покидает комнату чата;</span><span class="sxs-lookup"><span data-stu-id="57fe2-108">Leaves a chat room</span></span>

- <span data-ttu-id="57fe2-109">публикует сообщение;</span><span class="sxs-lookup"><span data-stu-id="57fe2-109">Posts a message</span></span>

- <span data-ttu-id="57fe2-110">просматривает историю чата;</span><span class="sxs-lookup"><span data-stu-id="57fe2-110">Views chat history</span></span>

- <span data-ttu-id="57fe2-111">отправляет файл;</span><span class="sxs-lookup"><span data-stu-id="57fe2-111">Uploads a file</span></span>

- <span data-ttu-id="57fe2-112">загружает файл.</span><span class="sxs-lookup"><span data-stu-id="57fe2-112">Downloads a file</span></span>

<span data-ttu-id="57fe2-113">Эти сведения можно получить из базы данных SQL соответствия требованиям при необходимости.</span><span class="sxs-lookup"><span data-stu-id="57fe2-113">This information can be retrieved from the Compliance SQL database as needed.</span></span> 

> [!NOTE]
> <span data-ttu-id="57fe2-114">Сохраняемая беседа доступна в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="57fe2-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="57fe2-115">Такие же функции доступны в Teams.</span><span class="sxs-lookup"><span data-stu-id="57fe2-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="57fe2-116">Дополнительные сведения [см. в сведениях о том,](/microsoftteams/upgrade-start-here)как начать обновление Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="57fe2-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="57fe2-117">Если необходимо использовать сохраняемого чата, вы можете либо перенести пользователей, которым требуются эти функции, в Teams, либо продолжить использование Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="57fe2-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-the-compliance-service-by-using-windows-powershell"></a><span data-ttu-id="57fe2-118">Настройка службы соответствия с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="57fe2-118">Configure the Compliance service by using Windows PowerShell</span></span>

<span data-ttu-id="57fe2-119">После включения службы соответствия с помощью построитель топологий ее можно настроить с помощью cmdlet **Set-CsPersistenChatComplianceConfiguration:**</span><span class="sxs-lookup"><span data-stu-id="57fe2-119">After the Compliance service has been enabled by using the Topology Builder, you can configure the service by using the **Set-CsPersistenChatComplianceConfiguration** cmdlet:</span></span>

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

<span data-ttu-id="57fe2-120">или</span><span class="sxs-lookup"><span data-stu-id="57fe2-120">or</span></span>

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

<span data-ttu-id="57fe2-121">Можно установить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="57fe2-121">You can set the following parameters:</span></span>

- <span data-ttu-id="57fe2-122">AdapterType — позволяет указать тип адаптера.</span><span class="sxs-lookup"><span data-stu-id="57fe2-122">AdapterType - Lets you specify the adapter type.</span></span> <span data-ttu-id="57fe2-123">Адаптер — это сторонний продукт, который преобразует данные в базе данных соответствия в определенный формат.</span><span class="sxs-lookup"><span data-stu-id="57fe2-123">An adapter is a third-party product that converts the data in the compliance database to a specific format.</span></span> <span data-ttu-id="57fe2-124">XML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="57fe2-124">XML is the default.</span></span>

- <span data-ttu-id="57fe2-125">OneChatRoomPerOutputFile — этот параметр позволяет указать, что для каждой комнаты чата создаются отдельные отчеты.</span><span class="sxs-lookup"><span data-stu-id="57fe2-125">OneChatRoomPerOutputFile - This parameter lets you specify that separate reports to be created for each chat room.</span></span>

- <span data-ttu-id="57fe2-126">AddChatRoomDetails . Если этот параметр включен, этот параметр записи дополнительные сведения о каждой комнате чата в базе данных.</span><span class="sxs-lookup"><span data-stu-id="57fe2-126">AddChatRoomDetails - When enabled, this parameter records additional details about each chat room in the database.</span></span> <span data-ttu-id="57fe2-127">Поскольку этот параметр может значительно увеличить размер базы данных, он по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="57fe2-127">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>

- <span data-ttu-id="57fe2-128">AddUserDetails . Если этот параметр включен, этот параметр записи дополнительные сведения о каждом пользователе комнаты чата в базе данных.</span><span class="sxs-lookup"><span data-stu-id="57fe2-128">AddUserDetails - When enabled, this parameter records additional details about each chat room user in the database.</span></span> <span data-ttu-id="57fe2-129">Поскольку этот параметр может значительно увеличить размер базы данных, он по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="57fe2-129">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>

- <span data-ttu-id="57fe2-130">Identity — этот параметр позволяет устанавливать область действия параметров соответствия для определенной коллекции, включая глобальные уровни, уровни сайтов и служб.</span><span class="sxs-lookup"><span data-stu-id="57fe2-130">Identity - This parameter allows compliance settings to be scoped for a particular collection, including the global, site, and service levels.</span></span> <span data-ttu-id="57fe2-131">Значение по умолчанию — глобальный уровень.</span><span class="sxs-lookup"><span data-stu-id="57fe2-131">The default is the global level.</span></span> 

- <span data-ttu-id="57fe2-132">RunInterval — этот параметр определяет время, в течение времени до создания сервером следующего выходного файла соответствия требованиям (значение по умолчанию — 15 минут).</span><span class="sxs-lookup"><span data-stu-id="57fe2-132">RunInterval - This parameter dictates the amount of time before the server creates the next compliance output file (the default is 15 minutes).</span></span>

## <a name="use-a-customized-compliance-adapter"></a><span data-ttu-id="57fe2-133">Использование настроенного адаптера соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="57fe2-133">Use a customized compliance adapter</span></span>

<span data-ttu-id="57fe2-134">Можно написать пользовательский адаптер вместо XmlAdapter, установленного с сервером сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="57fe2-134">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="57fe2-135">Для этого необходимо предоставить сборку .NET Framework, содержащую общий класс, который реализует интерфейс **IComplianceAdapter**.</span><span class="sxs-lookup"><span data-stu-id="57fe2-135">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="57fe2-136">Эту сборку необходимо разместить в папке установки сервера сохраняемого чата каждого сервера в пуле серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="57fe2-136">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="57fe2-137">Любой из серверов совместимости может предоставлять данные о совместимости адаптеру, но серверы совместимости не могут предоставлять дублированные данные о совместимости нескольким экземплярам адаптера.</span><span class="sxs-lookup"><span data-stu-id="57fe2-137">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<span data-ttu-id="57fe2-138">Интерфейс определяется в сборке Compliance.dll в пространстве  `Microsoft.Rtc.Internal.Chat.Server.Compliance` имен.</span><span class="sxs-lookup"><span data-stu-id="57fe2-138">The interface is defined in the Compliance.dll assembly in the namespace  `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="57fe2-139">В интерфейсе определены два метода, которые должен реализовать настраиваемый адаптер.</span><span class="sxs-lookup"><span data-stu-id="57fe2-139">The interface defines two methods that your custom adapter must implement.</span></span>

<span data-ttu-id="57fe2-140">Сервер соответствия сохраняемого чата будет вызывать следующий метод при первой загрузке адаптер.</span><span class="sxs-lookup"><span data-stu-id="57fe2-140">The Persistent Chat Compliance server will call the following method when the adapter first loads.</span></span> <span data-ttu-id="57fe2-141">Содержит  `AdapterConfig` конфигурацию соответствия сохраняемой беседы, соответствующую адаптеру соответствия:</span><span class="sxs-lookup"><span data-stu-id="57fe2-141">The  `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter:</span></span>

```cpp
void SetConfig(AdapterConfig config)
```

<span data-ttu-id="57fe2-142">Сервер соответствия сохраняемого чата периодически вызывает следующий метод, если имеются новые данные для перевода.</span><span class="sxs-lookup"><span data-stu-id="57fe2-142">The Persistent Chat Compliance server calls the following method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="57fe2-143">Этот интервал времени равен установленного в конфигурации соответствия  `RunInterval` сохраняемой беседы:</span><span class="sxs-lookup"><span data-stu-id="57fe2-143">This time interval is equal to the  `RunInterval` as set in the Persistent Chat Compliance configuration:</span></span>

```cpp
void Translate(ConversationCollection conversations)
```

<span data-ttu-id="57fe2-144">Содержит  `ConversationCollection` сведения о беседе, собранные с последнего метода.</span><span class="sxs-lookup"><span data-stu-id="57fe2-144">The  `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

## <a name="customize-the-xslt-definition-file"></a><span data-ttu-id="57fe2-145">Настройка файла определения XSLT</span><span class="sxs-lookup"><span data-stu-id="57fe2-145">Customize the XSLT definition file</span></span>

<span data-ttu-id="57fe2-146">Данные соответствия доставляются в формате XML, который можно преобразовать в формат, который лучше всего подходит для вашей организации, с помощью XSLT-файла определения.</span><span class="sxs-lookup"><span data-stu-id="57fe2-146">The compliance data is delivered as XML, which you can transform into the format that best fits your organization, by using an XSLT definition file.</span></span> <span data-ttu-id="57fe2-147">В этом разделе описывается XML-файл, который создает служба соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="57fe2-147">This topic describes the XML file that the Compliance service creates.</span></span> <span data-ttu-id="57fe2-148">Он также предоставляет примеры XSLT-файлов определений и выходных файлов.</span><span class="sxs-lookup"><span data-stu-id="57fe2-148">It also provides samples of XSLT definition and output files.</span></span>

### <a name="output-format"></a><span data-ttu-id="57fe2-149">Формат выходных данных</span><span class="sxs-lookup"><span data-stu-id="57fe2-149">Output format</span></span>

<span data-ttu-id="57fe2-150">Выходные данные службы соответствия классифицируются по беседе (элемент Conversation), а затем по сообщению (элемент Messages), как показано в следующем примере кода:</span><span class="sxs-lookup"><span data-stu-id="57fe2-150">The Compliance service output is categorized by conversation (the Conversation element) and then by message (the Messages element), as shown in the following code sample:</span></span>

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

<span data-ttu-id="57fe2-151">Элемент Conversation содержит четыре элемента (Channel, FirstMessage, StartTimeUTC и EndTimeUTC).</span><span class="sxs-lookup"><span data-stu-id="57fe2-151">A Conversation element contains four elements (Channel, FirstMessage, StartTimeUTC, and EndTimeUTC).</span></span> <span data-ttu-id="57fe2-152">Элемент Channel содержит URI-код комнаты чата, а элемент FirstMessage описывает первое сообщение в элементе Messages.</span><span class="sxs-lookup"><span data-stu-id="57fe2-152">The Channel element contains the Uniform Resource Identifier (URI) of the chat room, and the FirstMessage element describes the first message in the Messages element.</span></span> <span data-ttu-id="57fe2-153">Элементы StartTimeUTC и EndTimeUTC предоставляют время начала и окончания беседы, как показано в следующем примере кода:</span><span class="sxs-lookup"><span data-stu-id="57fe2-153">The StartTimeUTC and EndTimeUTC elements provide the start and end times for the conversation, as shown in the following code sample:</span></span>

```xml
<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

<span data-ttu-id="57fe2-154">Элемент Message содержит два элемента (Sender и DateTimeUTC) и три атрибута (Type, Content и ID).</span><span class="sxs-lookup"><span data-stu-id="57fe2-154">A Message element contains two elements (Sender and DateTimeUTC) and three attributes (Type, Content, and ID).</span></span> <span data-ttu-id="57fe2-155">Элемент Sender представляет пользователя, отправившего сообщение, а элемент DateTimeUTC — время возникновения события, как показано в следующем примере кода:</span><span class="sxs-lookup"><span data-stu-id="57fe2-155">The Sender element represents the user who sends the message, and the DateTimeUTC element represents when an event occurs, as shown in the following code sample:</span></span>

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

<span data-ttu-id="57fe2-156">В следующей таблице показаны атрибуты сообщений Type, Content и ID.</span><span class="sxs-lookup"><span data-stu-id="57fe2-156">The following table describes the message attributes Type, Content, and ID.</span></span>

<span data-ttu-id="57fe2-157">**Атрибуты элемента Messages**</span><span class="sxs-lookup"><span data-stu-id="57fe2-157">**Messages Element Attributes**</span></span>

|<span data-ttu-id="57fe2-158">**Атрибут**</span><span class="sxs-lookup"><span data-stu-id="57fe2-158">**Attribute**</span></span>|<span data-ttu-id="57fe2-159">**Описание**</span><span class="sxs-lookup"><span data-stu-id="57fe2-159">**Description**</span></span>|<span data-ttu-id="57fe2-160">**Необязательный/необходимый**</span><span class="sxs-lookup"><span data-stu-id="57fe2-160">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="57fe2-161">Тип</span><span class="sxs-lookup"><span data-stu-id="57fe2-161">Type</span></span>  <br/> |<span data-ttu-id="57fe2-p114">Указывает тип сообщения. Типы сообщений описаны в таблице типов сообщений элемента Message.</span><span class="sxs-lookup"><span data-stu-id="57fe2-p114">Specifies the message type. The message types are described in the Message Elements Message Types table.</span></span>  <br/> |<span data-ttu-id="57fe2-164">Обязательно</span><span class="sxs-lookup"><span data-stu-id="57fe2-164">Required</span></span>  <br/> |
|<span data-ttu-id="57fe2-165">Контент</span><span class="sxs-lookup"><span data-stu-id="57fe2-165">Content</span></span>  <br/> |<span data-ttu-id="57fe2-p115">Представляет собой содержимое сообщения. Для сообщений с типом Join или Part этот атрибут не используется.</span><span class="sxs-lookup"><span data-stu-id="57fe2-p115">Contains the content of the message. Messages with a Type of Join or Part do not use this attribute.</span></span>  <br/> |<span data-ttu-id="57fe2-168">Необязательный</span><span class="sxs-lookup"><span data-stu-id="57fe2-168">Optional</span></span>  <br/> |
|<span data-ttu-id="57fe2-169">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="57fe2-169">ID</span></span>  <br/> |<span data-ttu-id="57fe2-p116">Указывает уникальный идентификатор содержимого. Этот атрибут используется только с сообщениями, имеющими тип Chat.</span><span class="sxs-lookup"><span data-stu-id="57fe2-p116">Specifies the unique ID of the content. This attribute is used only with messages with a Type of Chat.</span></span>  <br/> |<span data-ttu-id="57fe2-172">Необязательный</span><span class="sxs-lookup"><span data-stu-id="57fe2-172">Optional</span></span>  <br/> |

<span data-ttu-id="57fe2-p117">Каждый элемент Sender содержит пять атрибутов: имя пользователя, идентификатор, адрес электронной почты, принадлежность ко внутренним пользователям и URI-код. Эти атрибуты описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="57fe2-p117">Each Sender element contains five attributes: the user name, ID, email, internal, and URI. These attributes are described in the following table.</span></span>

<span data-ttu-id="57fe2-175">**Атрибуты элемента Sender**</span><span class="sxs-lookup"><span data-stu-id="57fe2-175">**Sender Element Attributes**</span></span>

|<span data-ttu-id="57fe2-176">**Атрибут**</span><span class="sxs-lookup"><span data-stu-id="57fe2-176">**Attribute**</span></span>|<span data-ttu-id="57fe2-177">**Описание**</span><span class="sxs-lookup"><span data-stu-id="57fe2-177">**Description**</span></span>|<span data-ttu-id="57fe2-178">**Необязательный/необходимый**</span><span class="sxs-lookup"><span data-stu-id="57fe2-178">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="57fe2-179">Имя пользователя</span><span class="sxs-lookup"><span data-stu-id="57fe2-179">Username</span></span>  <br/> |<span data-ttu-id="57fe2-180">Имя отправителя.</span><span class="sxs-lookup"><span data-stu-id="57fe2-180">The name of the sender.</span></span>  <br/> |<span data-ttu-id="57fe2-181">Необязательный</span><span class="sxs-lookup"><span data-stu-id="57fe2-181">Optional</span></span>  <br/> |
|<span data-ttu-id="57fe2-182">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="57fe2-182">ID</span></span>  <br/> |<span data-ttu-id="57fe2-183">Уникальный ИД отправитель.</span><span class="sxs-lookup"><span data-stu-id="57fe2-183">The sender's unique ID.</span></span>  <br/> |<span data-ttu-id="57fe2-184">Обязательно</span><span class="sxs-lookup"><span data-stu-id="57fe2-184">Required</span></span>  <br/> |
|<span data-ttu-id="57fe2-185">Электронный адрес</span><span class="sxs-lookup"><span data-stu-id="57fe2-185">Email</span></span>  <br/> |<span data-ttu-id="57fe2-186">Электронный адрес отправителя.</span><span class="sxs-lookup"><span data-stu-id="57fe2-186">The sender's email address.</span></span>  <br/> |<span data-ttu-id="57fe2-187">Необязательный</span><span class="sxs-lookup"><span data-stu-id="57fe2-187">Optional</span></span>  <br/> |
|<span data-ttu-id="57fe2-188">Внутренний</span><span class="sxs-lookup"><span data-stu-id="57fe2-188">Internal</span></span>  <br/> |<span data-ttu-id="57fe2-p118">Определяет, является ли пользователь внутренним или федеративным. Если задано значение true, пользователь является внутренним.</span><span class="sxs-lookup"><span data-stu-id="57fe2-p118">Determines whether the user is an internal user or a federated user. If the value is set to true, the user is internal.</span></span>  <br/> |<span data-ttu-id="57fe2-191">Необязательный</span><span class="sxs-lookup"><span data-stu-id="57fe2-191">Optional</span></span>  <br/> |
|<span data-ttu-id="57fe2-192">Uri</span><span class="sxs-lookup"><span data-stu-id="57fe2-192">Uri</span></span>  <br/> |<span data-ttu-id="57fe2-193">URI SIP пользователя.</span><span class="sxs-lookup"><span data-stu-id="57fe2-193">The user's SIP URI.</span></span>  <br/> |<span data-ttu-id="57fe2-194">Обязательно</span><span class="sxs-lookup"><span data-stu-id="57fe2-194">Required</span></span>  <br/> |

<span data-ttu-id="57fe2-195">В следующих примерах покажите типы сообщений, которые может содержать элемент Messages.</span><span class="sxs-lookup"><span data-stu-id="57fe2-195">The following examples show the message types that the Messages element can contain.</span></span> <span data-ttu-id="57fe2-196">Здесь также представлен пример использования каждого из элементов.</span><span class="sxs-lookup"><span data-stu-id="57fe2-196">It also provides examples of how each element is used.</span></span>

<span data-ttu-id="57fe2-197">Join — пользователь присоединяется к комнате чата.</span><span class="sxs-lookup"><span data-stu-id="57fe2-197">Join - A user joins a chat room.</span></span>

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

<span data-ttu-id="57fe2-198">Часть— пользователь покидает комнату чата.</span><span class="sxs-lookup"><span data-stu-id="57fe2-198">Part - A user leaves a chat room.</span></span>

```xml
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

<span data-ttu-id="57fe2-199">Чат — адрес электронной почты отправитель.</span><span class="sxs-lookup"><span data-stu-id="57fe2-199">Chat - The sender's email address.</span></span>

```xml
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

<span data-ttu-id="57fe2-200">Backchat — пользователь запрашивает содержимое из истории чата.</span><span class="sxs-lookup"><span data-stu-id="57fe2-200">Backchat - A user requests content from chat history.</span></span>

```xml
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

<span data-ttu-id="57fe2-201">Отправка файла — пользователь загружает файл.</span><span class="sxs-lookup"><span data-stu-id="57fe2-201">File upload - A user uploads a file.</span></span>

```xml
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

<span data-ttu-id="57fe2-202">Загрузка файла— пользователь скачивает файл.</span><span class="sxs-lookup"><span data-stu-id="57fe2-202">File download - A user downloads a file.</span></span>

```xml
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a><span data-ttu-id="57fe2-203">XSD-данные сохраняемой беседы по умолчанию и пример преобразования XSL</span><span class="sxs-lookup"><span data-stu-id="57fe2-203">Default Persistent Chat Output XSD and Example XSL Transform</span></span>

<span data-ttu-id="57fe2-204">Следующий пример кода содержит выходные данные по умолчанию с сервера соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="57fe2-204">The following code sample contains the default output from the Compliance Server:</span></span>

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

<span data-ttu-id="57fe2-205">В следующем примере кода содержится пример преобразования XSL:</span><span class="sxs-lookup"><span data-stu-id="57fe2-205">The following code sample contains a sample XSL transform:</span></span>

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
