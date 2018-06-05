---
title: Настройка службы проверки на соответствие для сервера сохраняемого чата в Skype для бизнеса Server 2015
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
ms.openlocfilehash: 99c09408fbc404edd7ccd6c3844f59dca77a35f0
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568628"
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="0e6e3-103">Настройка службы проверки на соответствие для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="0e6e3-103">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0e6e3-104">**Сводка:** Узнайте, как настроить службу соответствия Persistent Chat Server в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-104">**Summary:** Learn how to configure the Persistent Chat Server Compliance service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="0e6e3-105">Проверка совместимости сохраняемого чата позволяет администраторам хранить архив сообщений сохраняемого чата и действий в нем.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-105">Persistent Chat compliance lets administrators maintain an archive of Persistent Chat messages as well as activities.</span></span> <span data-ttu-id="0e6e3-106">Служба соответствия записей и архивов данные, связанные с каждой беседы сервера сохраняемого чата, в том числе участника:</span><span class="sxs-lookup"><span data-stu-id="0e6e3-106">The Compliance service records and archives data related to each Persistent Chat Server conversation, including when a participant:</span></span>
  
- <span data-ttu-id="0e6e3-107">Операторы комнаты сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="0e6e3-107">Joins a Persistent Chat room</span></span>
    
- <span data-ttu-id="0e6e3-108">покидает комнату чата;</span><span class="sxs-lookup"><span data-stu-id="0e6e3-108">Leaves a chat room</span></span>
    
- <span data-ttu-id="0e6e3-109">публикует сообщение;</span><span class="sxs-lookup"><span data-stu-id="0e6e3-109">Posts a message</span></span>
    
- <span data-ttu-id="0e6e3-110">просматривает историю чата;</span><span class="sxs-lookup"><span data-stu-id="0e6e3-110">Views chat history</span></span>
    
- <span data-ttu-id="0e6e3-111">отправляет файл;</span><span class="sxs-lookup"><span data-stu-id="0e6e3-111">Uploads a file</span></span>
    
- <span data-ttu-id="0e6e3-112">загружает файл.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-112">Downloads a file</span></span>
    
<span data-ttu-id="0e6e3-113">Эта информация может извлекаться из базы данных проверки совместимости SQL по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-113">This information can be retrieved from the Compliance SQL database as needed.</span></span> 
  
## <a name="configure-the-compliance-service-by-using-windows-powershell"></a><span data-ttu-id="0e6e3-114">Настройка службы проверки совместимости с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e6e3-114">Configure the Compliance service by using Windows PowerShell</span></span>

<span data-ttu-id="0e6e3-115">Включив службы проверки совместимости с помощью построителя топологий, можно настроить ее путем выполнения командлета **Set-CsPersistenChatComplianceConfiguration**:</span><span class="sxs-lookup"><span data-stu-id="0e6e3-115">After the Compliance service has been enabled by using the Topology Builder, you can configure the service by using the **Set-CsPersistenChatComplianceConfiguration** cmdlet:</span></span>
  
```
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

<span data-ttu-id="0e6e3-116">или</span><span class="sxs-lookup"><span data-stu-id="0e6e3-116">or</span></span>
  
```
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

<span data-ttu-id="0e6e3-117">Можно задать следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-117">You can set the following parameters:</span></span>
  
- <span data-ttu-id="0e6e3-118">AdapterType - позволяет указать тип адаптера.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-118">AdapterType - Lets you specify the adapter type.</span></span> <span data-ttu-id="0e6e3-119">Адаптер — это продукт сторонних производителей, который преобразует данные в базе данных соответствия требованиям в определенный формат.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-119">An adapter is a third-party product that converts the data in the compliance database to a specific format.</span></span> <span data-ttu-id="0e6e3-120">По умолчанию выполняется XML.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-120">XML is the default.</span></span>
    
- <span data-ttu-id="0e6e3-121">OneChatRoomPerOutputFile — этот параметр позволяет указать, что, разделите отчеты должны быть созданы для каждой чат.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-121">OneChatRoomPerOutputFile - This parameter lets you specify that separate reports to be created for each chat room.</span></span>
    
- <span data-ttu-id="0e6e3-122">AddChatRoomDetails - при включении этого параметра, этот параметр записывает Дополнительные сведения о каждом комнаты чата в базе данных.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-122">AddChatRoomDetails - When enabled, this parameter records additional details about each chat room in the database.</span></span> <span data-ttu-id="0e6e3-123">Поскольку этот параметр может существенно увеличить размер базы данных, он отключен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-123">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>
    
- <span data-ttu-id="0e6e3-124">AddUserDetails - при включении этого параметра, этот параметр записывает Дополнительные сведения о каждом пользователе комнаты чата в базе данных.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-124">AddUserDetails - When enabled, this parameter records additional details about each chat room user in the database.</span></span> <span data-ttu-id="0e6e3-125">Поскольку этот параметр может существенно увеличить размер базы данных, он отключен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-125">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>
    
- <span data-ttu-id="0e6e3-126">Удостоверение — этот параметр позволяет параметров соответствия требованиям для ограничения области для определенного семейства сайтов, включая глобальной, сайта и уровни обслуживания.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-126">Identity - This parameter allows compliance settings to be scoped for a particular collection, including the global, site, and service levels.</span></span> <span data-ttu-id="0e6e3-127">Значение по умолчанию — глобальный уровень.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-127">The default is the global level.</span></span> 
    
- <span data-ttu-id="0e6e3-128">RunInterval. Этот параметр определяет длительность периода, по истечении которого на сервере создается новый выходной файл проверки совместимости (по умолчанию: 15 минут).</span><span class="sxs-lookup"><span data-stu-id="0e6e3-128">RunInterval - This parameter dictates the amount of time before the server creates the next compliance output file (the default is 15 minutes).</span></span>
    
## <a name="use-a-customized-compliance-adapter"></a><span data-ttu-id="0e6e3-129">Работа с пользовательским адаптером проверки совместимости</span><span class="sxs-lookup"><span data-stu-id="0e6e3-129">Use a customized compliance adapter</span></span>

<span data-ttu-id="0e6e3-130">Можно написать пользовательский адаптер вместо использования адаптера xmladapter настраиваемым, который устанавливается вместе с сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-130">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="0e6e3-131">Для этого необходимо предоставить сборку .NET Framework, которая содержит общий класс, реализующий интерфейс **IComplianceAdapter**.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-131">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="0e6e3-132">Эта сборка необходимо поместить в папку установки сервера сохраняемого чата каждого сервера в пуле серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-132">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="0e6e3-133">Данные проверки совместимости могут поступать в адаптер с любого сервера проверки совместимости, но на разные экземпляры адаптера с серверов проверки совместимости на поступают повторяющиеся данные.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-133">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>
  
<span data-ttu-id="0e6e3-134">Интерфейс определен в сборке Compliance.dll в пространстве имен `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-134">The interface is defined in the Compliance.dll assembly in the namespace  `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="0e6e3-135">Интерфейс определяет два метода, которые должен реализовать пользовательский адаптер.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-135">The interface defines two methods that your custom adapter must implement.</span></span>
  
<span data-ttu-id="0e6e3-136">Сервер соответствия Persistent Chat будет вызвать метод следующие при первой загрузке адаптера.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-136">The Persistent Chat Compliance server will call the following method when the adapter first loads.</span></span> <span data-ttu-id="0e6e3-137">`AdapterConfig` Содержит конфигурацию соответствия Persistent Chat, соответствующий адаптеру соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="0e6e3-137">The  `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter:</span></span>
  
```
void SetConfig(AdapterConfig config)
```

<span data-ttu-id="0e6e3-138">Соответствия Persistent Chat server вызывает следующий метод через определенные интервалы, поскольку новые данные для перевода.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-138">The Persistent Chat Compliance server calls the following method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="0e6e3-139">Этот период равен `RunInterval` как задано в конфигурации соответствия Persistent Chat:</span><span class="sxs-lookup"><span data-stu-id="0e6e3-139">This time interval is equal to the  `RunInterval` as set in the Persistent Chat Compliance configuration:</span></span>
  
```
void Translate(ConversationCollection conversations)
```

<span data-ttu-id="0e6e3-140">`ConversationCollection` Содержит сведения о беседах, собранные с момента последнего последнем вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-140">The  `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>
  
## <a name="customize-the-xslt-definition-file"></a><span data-ttu-id="0e6e3-141">Настройка файла определения XSLT</span><span class="sxs-lookup"><span data-stu-id="0e6e3-141">Customize the XSLT definition file</span></span>

<span data-ttu-id="0e6e3-p110">Данные проверки совместимости доставляются в формате XML, который можно с применением файла определения XSLT преобразовать в формат, подходящий для конкретной организации. Этот раздел содержит описание файла XML, созданного с помощью службы проверки совместимости. Приведены также примеры файла определения XSLT и выходного файла.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-p110">The compliance data is delivered as XML, which you can transform into the format that best fits your organization, by using an XSLT definition file. This topic describes the XML file that the Compliance service creates. It also provides samples of XSLT definition and output files.</span></span>
  
### <a name="output-format"></a><span data-ttu-id="0e6e3-145">Форма выходных данных</span><span class="sxs-lookup"><span data-stu-id="0e6e3-145">Output format</span></span>

<span data-ttu-id="0e6e3-146">Выходные данные службы проверки совместимости классифицируются по беседе (элемент Conversation) и затем по сообщению (элемент Messages), как показано в следующем примере кода:</span><span class="sxs-lookup"><span data-stu-id="0e6e3-146">The Compliance service output is categorized by conversation (the Conversation element) and then by message (the Messages element), as shown in the following code sample:</span></span>
  
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

<span data-ttu-id="0e6e3-p111">Элемент Conversation содержит четыре элемента (Channel, FirstMessage, StartTimeUTC и EndTimeUTC). Элемент Channel содержит код URI, назначенный комнате чата, а элемент FirstMessage описывает первое сообщение в элементе Messages. Элементы StartTimeUTC и EndTimeUTC задают время начала и окончания беседы, как показано в следующем примере кода:</span><span class="sxs-lookup"><span data-stu-id="0e6e3-p111">A Conversation element contains four elements (Channel, FirstMessage, StartTimeUTC, and EndTimeUTC). The Channel element contains the Uniform Resource Identifier (URI) of the chat room, and the FirstMessage element describes the first message in the Messages element. The StartTimeUTC and EndTimeUTC elements provide the start and end times for the conversation, as shown in the following code sample:</span></span>
  
```
<<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

<span data-ttu-id="0e6e3-p112">Элемент Message содержит два элемента (Sender и DateTimeUTC) и три атрибута (Type, Content и ID). Элемент Sender представляет пользователя, отправляющего сообщение, а элемент DateTimeUTC — время возникновения события, как показано в следующем примере кода:</span><span class="sxs-lookup"><span data-stu-id="0e6e3-p112">A Message element contains two elements (Sender and DateTimeUTC) and three attributes (Type, Content, and ID). The Sender element represents the user who sends the message, and the DateTimeUTC element represents when an event occurs, as shown in the following code sample:</span></span>
  
```
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

<span data-ttu-id="0e6e3-152">В следующей таблице показаны атрибуты сообщений Type, Content и ID.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-152">The following table describes the message attributes Type, Content, and ID.</span></span>
  
<span data-ttu-id="0e6e3-153">**Атрибуты элемента messages**</span><span class="sxs-lookup"><span data-stu-id="0e6e3-153">**Messages Element Attributes**</span></span>

|<span data-ttu-id="0e6e3-154">**Атрибут**</span><span class="sxs-lookup"><span data-stu-id="0e6e3-154">**Attribute**</span></span>|<span data-ttu-id="0e6e3-155">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0e6e3-155">**Description**</span></span>|<span data-ttu-id="0e6e3-156">**Необязательный или обязательный**</span><span class="sxs-lookup"><span data-stu-id="0e6e3-156">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0e6e3-157">Тип</span><span class="sxs-lookup"><span data-stu-id="0e6e3-157">Type</span></span>  <br/> |<span data-ttu-id="0e6e3-p113">Указывает тип сообщения. Типы сообщений описаны в таблице типов сообщений элемента Message.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-p113">Specifies the message type. The message types are described in the Message Elements Message Types table.</span></span>  <br/> |<span data-ttu-id="0e6e3-160">Обязательный</span><span class="sxs-lookup"><span data-stu-id="0e6e3-160">Required</span></span>  <br/> |
|<span data-ttu-id="0e6e3-161">Content</span><span class="sxs-lookup"><span data-stu-id="0e6e3-161">Content</span></span>  <br/> |<span data-ttu-id="0e6e3-p114">Представляет собой содержимое сообщения. Для сообщений с типом Join или Part этот атрибут не используется.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-p114">Contains the content of the message. Messages with a Type of Join or Part do not use this attribute.</span></span>  <br/> |<span data-ttu-id="0e6e3-164">Необязательный</span><span class="sxs-lookup"><span data-stu-id="0e6e3-164">Optional</span></span>  <br/> |
|<span data-ttu-id="0e6e3-165">ID</span><span class="sxs-lookup"><span data-stu-id="0e6e3-165">ID</span></span>  <br/> |<span data-ttu-id="0e6e3-p115">Указывает уникальный идентификатор содержимого. Этот атрибут используется только с сообщениями, имеющими тип Chat.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-p115">Specifies the unique ID of the content. This attribute is used only with messages with a Type of Chat.</span></span>  <br/> |<span data-ttu-id="0e6e3-168">Необязательный</span><span class="sxs-lookup"><span data-stu-id="0e6e3-168">Optional</span></span>  <br/> |
   
<span data-ttu-id="0e6e3-p116">Каждый элемент Sender содержит пять атрибутов: имя пользователя, идентификатор, адрес электронной почты, принадлежность ко внутренним пользователям и URI-код. Эти атрибуты описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-p116">Each Sender element contains five attributes: the user name, ID, email, internal, and URI. These attributes are described in the following table.</span></span>
  
<span data-ttu-id="0e6e3-171">**Атрибуты элемента sender**</span><span class="sxs-lookup"><span data-stu-id="0e6e3-171">**Sender Element Attributes**</span></span>

|<span data-ttu-id="0e6e3-172">**Атрибут**</span><span class="sxs-lookup"><span data-stu-id="0e6e3-172">**Attribute**</span></span>|<span data-ttu-id="0e6e3-173">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0e6e3-173">**Description**</span></span>|<span data-ttu-id="0e6e3-174">**Необязательный или обязательный**</span><span class="sxs-lookup"><span data-stu-id="0e6e3-174">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0e6e3-175">Username</span><span class="sxs-lookup"><span data-stu-id="0e6e3-175">Username</span></span>  <br/> |<span data-ttu-id="0e6e3-176">Имя отправителя.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-176">The name of the sender.</span></span>  <br/> |<span data-ttu-id="0e6e3-177">Необязательный</span><span class="sxs-lookup"><span data-stu-id="0e6e3-177">Optional</span></span>  <br/> |
|<span data-ttu-id="0e6e3-178">ID</span><span class="sxs-lookup"><span data-stu-id="0e6e3-178">ID</span></span>  <br/> |<span data-ttu-id="0e6e3-179">Уникальный идентификатор отправителя.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-179">The sender's unique ID.</span></span>  <br/> |<span data-ttu-id="0e6e3-180">Обязательный</span><span class="sxs-lookup"><span data-stu-id="0e6e3-180">Required</span></span>  <br/> |
|<span data-ttu-id="0e6e3-181">Email</span><span class="sxs-lookup"><span data-stu-id="0e6e3-181">Email</span></span>  <br/> |<span data-ttu-id="0e6e3-182">Адрес электронной почты отправителя.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-182">The sender's email address.</span></span>  <br/> |<span data-ttu-id="0e6e3-183">Необязательный</span><span class="sxs-lookup"><span data-stu-id="0e6e3-183">Optional</span></span>  <br/> |
|<span data-ttu-id="0e6e3-184">Internal</span><span class="sxs-lookup"><span data-stu-id="0e6e3-184">Internal</span></span>  <br/> |<span data-ttu-id="0e6e3-p117">Определяет, является ли пользователь внутренним или федеративным. Если задано значение true, пользователь является внутренним.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-p117">Determines whether the user is an internal user or a federated user. If the value is set to true, the user is internal.</span></span>  <br/> |<span data-ttu-id="0e6e3-187">Необязательный</span><span class="sxs-lookup"><span data-stu-id="0e6e3-187">Optional</span></span>  <br/> |
|<span data-ttu-id="0e6e3-188">Uri</span><span class="sxs-lookup"><span data-stu-id="0e6e3-188">Uri</span></span>  <br/> |<span data-ttu-id="0e6e3-189">URI SIP пользователя.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-189">The user's SIP URI.</span></span>  <br/> |<span data-ttu-id="0e6e3-190">Обязательно</span><span class="sxs-lookup"><span data-stu-id="0e6e3-190">Required</span></span>  <br/> |
   
<span data-ttu-id="0e6e3-191">В следующих примерах показано типы сообщений, которые может содержать элемент сообщения.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-191">The following examples show the message types that the Messages element can contain.</span></span> <span data-ttu-id="0e6e3-192">Здесь также представлен пример использования каждого из элементов.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-192">It also provides examples of how each element is used.</span></span>
  
<span data-ttu-id="0e6e3-193">Соединение — пользователь присоединяется к комнате чата.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-193">Join - A user joins a chat room.</span></span>
  
```
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

<span data-ttu-id="0e6e3-194">Часть — пользователь покидает комнату чата.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-194">Part - A user leaves a chat room.</span></span>
  
```
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

<span data-ttu-id="0e6e3-195">Чат - адрес электронной почты отправителя.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-195">Chat - The sender's email address.</span></span>
  
```
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

<span data-ttu-id="0e6e3-196">Ответ на чат - пользователь запрашивает содержимое из истории чата.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-196">Backchat - A user requests content from chat history.</span></span>
  
```
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

<span data-ttu-id="0e6e3-197">Отправка файла - пользователь отправляет файл.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-197">File upload - A user uploads a file.</span></span>
  
```
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

<span data-ttu-id="0e6e3-198">Загрузка файла — пользователь загружает файл.</span><span class="sxs-lookup"><span data-stu-id="0e6e3-198">File download - A user downloads a file.</span></span>
  
```
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a><span data-ttu-id="0e6e3-199">По умолчанию выходные данные сохраняемого чата XSD и пример преобразования XSL</span><span class="sxs-lookup"><span data-stu-id="0e6e3-199">Default Persistent Chat Output XSD and Example XSL Transform</span></span>

<span data-ttu-id="0e6e3-200">Следующий пример кода содержит выходные данные сервера проверки совместимости по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="0e6e3-200">The following code sample contains the default output from the Compliance Server:</span></span>
  
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

<span data-ttu-id="0e6e3-201">Следующий образец кода содержит пример преобразования в формат XSL:</span><span class="sxs-lookup"><span data-stu-id="0e6e3-201">The following code sample contains a sample XSL transform:</span></span>
  
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