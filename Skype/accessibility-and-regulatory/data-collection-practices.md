---
title: "Методы коллекции данных"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Legal
description: Microsoft collects census, usage, and error data to understand how Skype for Business is being used and where users encounter problems. The data is used to plan product improvements.
ms.openlocfilehash: 61f3e627883151eaf194b8ac4f4b4023e8624e48
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2017
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a><span data-ttu-id="b1c30-104">Рекомендации по сбору данных для Skype для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b1c30-104">Skype for Business and Microsoft Teams data collection practices</span></span>

<span data-ttu-id="b1c30-105">Скайп для Business Server 2015, Скайп для бизнеса в Интернет, а также Скайп для бизнеса и группами Майкрософт приложений сбор данных, которые помогут понять, как используются такие продукты и произошли какие виды ошибок, таких как ошибки входа в Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b1c30-105">Skype for Business Server 2015, Skype for Business Online, along with Skype for Business and Microsoft Teams apps collect data to help Microsoft understand how these products are being used and what kinds of errors, such as sign-in errors, have occurred.</span></span> <span data-ttu-id="b1c30-106">Эта информация поможет понять особенности использования, планирование новых функций и диагностике и устранении проблем.</span><span class="sxs-lookup"><span data-stu-id="b1c30-106">This information helps us understand usage patterns, plan new features, and troubleshoot and fix problem areas.</span></span>
  
<span data-ttu-id="b1c30-p103">Данные об использовании собираются автоматические, все другие данные могут быть собраны только с разрешения администратора и/или пользователя. Сбор данных делится на три категории:</span><span class="sxs-lookup"><span data-stu-id="b1c30-p103">While some usage data is collected automatically, other data can only be collected when the admin and/or user chooses to allow it. Data collection falls into these three categories:</span></span>
  
- <span data-ttu-id="b1c30-109">Данные переписи</span><span class="sxs-lookup"><span data-stu-id="b1c30-109">Census data</span></span>
    
- <span data-ttu-id="b1c30-110">Данные по использованию</span><span class="sxs-lookup"><span data-stu-id="b1c30-110">Usage data</span></span>
    
- <span data-ttu-id="b1c30-111">Предоставляемые отчеты об ошибках</span><span class="sxs-lookup"><span data-stu-id="b1c30-111">Error reporting data</span></span>
    
## <a name="census-data"></a><span data-ttu-id="b1c30-112">Данные переписи</span><span class="sxs-lookup"><span data-stu-id="b1c30-112">Census data</span></span>

<span data-ttu-id="b1c30-113">Данные переписи предоставляется исключительно для предоставления, поддержки и улучшения Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="b1c30-113">Census data is acquired solely to provide, support, and improve Skype for Business.</span></span> <span data-ttu-id="b1c30-114">Группами Майкрософт и Скайп для бизнеса в Интернете.</span><span class="sxs-lookup"><span data-stu-id="b1c30-114">Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="b1c30-115">Оно включает в себя окружающей среды сведения, такие как версии устройства и операционной системы и региональные и языковые параметры.</span><span class="sxs-lookup"><span data-stu-id="b1c30-115">It includes environmental information such as device and operating system versions, and regional and language settings.</span></span> <span data-ttu-id="b1c30-116">Он также включает счетчики попыток входа в систему и ошибок.</span><span class="sxs-lookup"><span data-stu-id="b1c30-116">It also includes counters for sign-in attempts and failures.</span></span> <span data-ttu-id="b1c30-117">Ниже приведены конкретные примеры переписные данные, собираемые:</span><span class="sxs-lookup"><span data-stu-id="b1c30-117">Here are some specific examples of the census data that's collected:</span></span>

|<span data-ttu-id="b1c30-118">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="b1c30-118">**Data type**</span></span>|<span data-ttu-id="b1c30-119">**Пример**</span><span class="sxs-lookup"><span data-stu-id="b1c30-119">**Example**</span></span>|<span data-ttu-id="b1c30-120">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="b1c30-120">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b1c30-121">Имя_приложения</span><span class="sxs-lookup"><span data-stu-id="b1c30-121">AppName</span></span>  <br/> |<span data-ttu-id="b1c30-122">iPhoneSkype</span><span class="sxs-lookup"><span data-stu-id="b1c30-122">iPhoneSkype</span></span>  <br/> ||
|<span data-ttu-id="b1c30-123">DeviceModel</span><span class="sxs-lookup"><span data-stu-id="b1c30-123">DeviceModel</span></span>  <br/> |<span data-ttu-id="b1c30-124">iPhone</span><span class="sxs-lookup"><span data-stu-id="b1c30-124">iPhone</span></span>  <br/> ||
|<span data-ttu-id="b1c30-125">Название ОС</span><span class="sxs-lookup"><span data-stu-id="b1c30-125">OSName</span></span>  <br/> |<span data-ttu-id="b1c30-126">iPhoneiOS</span><span class="sxs-lookup"><span data-stu-id="b1c30-126">iPhoneiOS</span></span>  <br/> ||
|<span data-ttu-id="b1c30-127">Версия ОС</span><span class="sxs-lookup"><span data-stu-id="b1c30-127">OSVersion</span></span>  <br/> |<span data-ttu-id="b1c30-128">в формате 8.3</span><span class="sxs-lookup"><span data-stu-id="b1c30-128">8.3</span></span>  <br/> ||
|<span data-ttu-id="b1c30-129">UserLanguage</span><span class="sxs-lookup"><span data-stu-id="b1c30-129">UserLanguage</span></span>  <br/> |<span data-ttu-id="b1c30-130">EN-US</span><span class="sxs-lookup"><span data-stu-id="b1c30-130">EN-US</span></span>  <br/> ||
|<span data-ttu-id="b1c30-131">Идентификатор пользователя</span><span class="sxs-lookup"><span data-stu-id="b1c30-131">UserID</span></span>  <br/> |<span data-ttu-id="b1c30-132">E296D735-4F36-4E18-7C3B-52E1A02A0164</span><span class="sxs-lookup"><span data-stu-id="b1c30-132">E296D735-4F36-4E18-7C3B-52E1A02A0164</span></span>  <br/> |<span data-ttu-id="b1c30-p105">Идентификатор хешируется дважды: первый раз в клиенте и затем в службе телеметрии. Хеширование гарантирует, что идентификатор не может быть связан с конкретным пользователем.</span><span class="sxs-lookup"><span data-stu-id="b1c30-p105">The ID is hashed twice: once on the client and again on the telemetry service. The hashing ensures the ID cannot be linked to a specific user.</span></span>  <br/> |
|<span data-ttu-id="b1c30-135">DeviceID</span><span class="sxs-lookup"><span data-stu-id="b1c30-135">DeviceID</span></span>  <br/> |<span data-ttu-id="b1c30-136">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span><span class="sxs-lookup"><span data-stu-id="b1c30-136">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span></span>  <br/> |<span data-ttu-id="b1c30-137">Идентификатор устройства  это глобальный уникальный идентификатор, который единожды генерируется на устройстве случайным образом и отправляется в службу телеметрии.</span><span class="sxs-lookup"><span data-stu-id="b1c30-137">The device ID is a GUID that's randomly generated once on the device and sent to the telemetry service.</span></span>  <br/> |
   
<span data-ttu-id="b1c30-p106">Данные переписи НЕ содержат информацию, идентифицирующую организацию или пользователя. Дополнительные сведения см. в разделе [Заявление о конфиденциальности Skype для бизнеса](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx).</span><span class="sxs-lookup"><span data-stu-id="b1c30-p106">Census data DOES NOT contain any information that identifies your organization or users. See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) for more information.</span></span>
  
<span data-ttu-id="b1c30-140">Данные переписи включены по умолчанию и не могут быть отключены администраторами или пользователями.</span><span class="sxs-lookup"><span data-stu-id="b1c30-140">Census data is on by default and cannot be turned off by admins or end users.</span></span>
  
## <a name="usage-data"></a><span data-ttu-id="b1c30-141">Данные по использованию</span><span class="sxs-lookup"><span data-stu-id="b1c30-141">Usage data</span></span>

<span data-ttu-id="b1c30-142">Данные по использованию содержат такую информацию, как количество совершенных вызов, количество отправленных или полученных сообщений, количество присоединенных собраний, частоту использования функций и проблемы, связанные со стабильностью.</span><span class="sxs-lookup"><span data-stu-id="b1c30-142">Usage data includes information such as number of calls made, number of IMs sent or received, number of meetings joined, frequency of features used, and stability issues.</span></span>
  
<span data-ttu-id="b1c30-143">Данные по использованию могут содержать информацию, идентифицирующую организацию, например, contoso.com. Ниже приведены конкретные примеры собранных данных по использованию:</span><span class="sxs-lookup"><span data-stu-id="b1c30-143">Usage data might contain information that identifies your organization, such as contoso.com. Here are some specific examples of the usage data that's collected:</span></span>
  
|<span data-ttu-id="b1c30-144">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="b1c30-144">**Data type**</span></span>|<span data-ttu-id="b1c30-145">**Пример**</span><span class="sxs-lookup"><span data-stu-id="b1c30-145">**Example**</span></span>|<span data-ttu-id="b1c30-146">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="b1c30-146">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b1c30-147">Отправлено сообщений</span><span class="sxs-lookup"><span data-stu-id="b1c30-147">IM Sent</span></span>  <br/> |<span data-ttu-id="b1c30-148">12</span><span class="sxs-lookup"><span data-stu-id="b1c30-148">12</span></span>  <br/> ||
|<span data-ttu-id="b1c30-149">Получено сообщений</span><span class="sxs-lookup"><span data-stu-id="b1c30-149">IM Received</span></span>  <br/> |<span data-ttu-id="b1c30-150">5</span><span class="sxs-lookup"><span data-stu-id="b1c30-150">5</span></span>  <br/> ||
|<span data-ttu-id="b1c30-151">Присоединение к собранию (попытки)</span><span class="sxs-lookup"><span data-stu-id="b1c30-151">Join a meeting (attempts)</span></span>  <br/> |<span data-ttu-id="b1c30-152">5</span><span class="sxs-lookup"><span data-stu-id="b1c30-152">5</span></span>  <br/> ||
|<span data-ttu-id="b1c30-153">Присоединение к собранию (успешно)</span><span class="sxs-lookup"><span data-stu-id="b1c30-153">Join a meeting (success)</span></span>  <br/> |<span data-ttu-id="b1c30-154">4</span><span class="sxs-lookup"><span data-stu-id="b1c30-154">4</span></span>  <br/> ||
|<span data-ttu-id="b1c30-155">Минуты вызовов/собраний</span><span class="sxs-lookup"><span data-stu-id="b1c30-155">Call/meeting minutes</span></span>  <br/> |<span data-ttu-id="b1c30-156">30 минут</span><span class="sxs-lookup"><span data-stu-id="b1c30-156">30 mins</span></span>  <br/> ||
|<span data-ttu-id="b1c30-157">FederationPartner</span><span class="sxs-lookup"><span data-stu-id="b1c30-157">FederationPartner</span></span>  <br/> |<span data-ttu-id="b1c30-158">Microsoft.com (en)</span><span class="sxs-lookup"><span data-stu-id="b1c30-158">Microsoft.com</span></span>  <br/> |<span data-ttu-id="b1c30-159">Это имя организации, зарегистрированное в Office 365 и переданное в открытом видео, т. е. без затенения.</span><span class="sxs-lookup"><span data-stu-id="b1c30-159">This is the name of the organization registered in Office 365 and is transmitted in cleartext, which means it's not obfuscated.</span></span>  <br/> |
   
<span data-ttu-id="b1c30-160">Данные по использованию НЕ содержат информацию, идентифицирующую пользователей.</span><span class="sxs-lookup"><span data-stu-id="b1c30-160">Usage data DOES NOT contain any information that identifies users.</span></span>
  
<span data-ttu-id="b1c30-p107">Сбор данных по использованию включен по умолчанию, но локальные администраторы могут отключить эту функцию с помощью параметра "Групповая политика DisableAutomaticSendTracing" в Skype для бизнеса Server 2015. Этот параметр отключается для всех пользователей в организации. См. раздел [Настройка политик начальной загрузки клиентов в Skype для бизнеса Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx).</span><span class="sxs-lookup"><span data-stu-id="b1c30-p107">Usage data collection is on by default, but on-premises admins can turn it off using the DisableAutomaticSendTracing Group Policy setting on Skype for Business Server 2015. Turning this setting off affects all users in the organization. See [Configure client bootstrapping policies in Skype for Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) for more information.</span></span>
  
<span data-ttu-id="b1c30-164">Конечные пользователи не могут включить или отключить сбор данных.</span><span class="sxs-lookup"><span data-stu-id="b1c30-164">End users cannot turn usage data collection on or off.</span></span>
  
<span data-ttu-id="b1c30-165">Управлять телеметрией для веб-страниц приложения для собраний Skype и агента присоединения можно с помощью следующей политики:</span><span class="sxs-lookup"><span data-stu-id="b1c30-165">For Skype Meetings App and the join launcher web pages, the way to control telemetry is through this policy:</span></span>
  
<span data-ttu-id="b1c30-166">Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True</span><span class="sxs-lookup"><span data-stu-id="b1c30-166">Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True</span></span>
  
<span data-ttu-id="b1c30-p108">Для этой политики по умолчанию установлено значение False, поэтому сбор данных телеметрии по умолчанию отключен. Этот параметр задается для каждого пула и позволяет управлять всеми пользователями, которые подключаются к собранию, проводимому на сервере, с помощью приложения для собраний Skype.</span><span class="sxs-lookup"><span data-stu-id="b1c30-p108">This policy defaults to false, so telemetry collection is off by default. This setting is per-pool and controls all users who connect with Skype Meetings App to a meeting hosted on that server.</span></span>
  
## <a name="error-reporting-data"></a><span data-ttu-id="b1c30-169">Предоставляемые отчеты об ошибках</span><span class="sxs-lookup"><span data-stu-id="b1c30-169">Error reporting data</span></span>

<span data-ttu-id="b1c30-p109">Предоставляемые отчеты об ошибках могут содержать информацию о производительности и надежности, конфигурации устройства, качестве сетевого подключения, кодах ошибок, журналах ошибок и исключениях. Ниже приведены конкретные примеры данных, собираемых в отчете об ошибках.</span><span class="sxs-lookup"><span data-stu-id="b1c30-p109">Error reporting data can include information about performance and reliability, device configuration, network connection quality, error codes, error logs, and exceptions. Here are some specific examples of error reporting data that's collected:</span></span>

|<span data-ttu-id="b1c30-172">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="b1c30-172">**Data type**</span></span>|<span data-ttu-id="b1c30-173">**Пример**</span><span class="sxs-lookup"><span data-stu-id="b1c30-173">**Example**</span></span>|<span data-ttu-id="b1c30-174">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="b1c30-174">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b1c30-175">Направление отправки сообщений</span><span class="sxs-lookup"><span data-stu-id="b1c30-175">Message direction</span></span>  <br/> |<span data-ttu-id="b1c30-176">Входящие</span><span class="sxs-lookup"><span data-stu-id="b1c30-176">Incoming</span></span>  <br/> ||
|<span data-ttu-id="b1c30-177">Состояние беседы</span><span class="sxs-lookup"><span data-stu-id="b1c30-177">Conversation state</span></span>  <br/> |<span data-ttu-id="b1c30-178">Неактивн.</span><span class="sxs-lookup"><span data-stu-id="b1c30-178">Idle</span></span>  <br/> ||
|<span data-ttu-id="b1c30-179">Идентификатор потока беседы</span><span class="sxs-lookup"><span data-stu-id="b1c30-179">Conversation thread ID</span></span>  <br/> |<span data-ttu-id="b1c30-180">AdDO8hsJqilU93hQHC3OZaPR2saEA ==</span><span class="sxs-lookup"><span data-stu-id="b1c30-180">AdDO8hsJqilU93hQHC3OZaPR2saEA==</span></span>  <br/> ||
|<span data-ttu-id="b1c30-181">Идентификатор пользователя</span><span class="sxs-lookup"><span data-stu-id="b1c30-181">UserID</span></span>  <br/> |<span data-ttu-id="b1c30-182">amosmarble</span><span class="sxs-lookup"><span data-stu-id="b1c30-182">amosmarble</span></span> <br/> |<span data-ttu-id="b1c30-183">Идентификатор отправляется в открытом виде, который хэшируется службой телеметрии перед сохранением</span><span class="sxs-lookup"><span data-stu-id="b1c30-183">The ID is sent in cleartext , which the telemetry service hashes before storing it</span></span>  <br/> |
   
<span data-ttu-id="b1c30-p110">Сведения, собираемые в отчете об ошибках, содержат личную информацию, включая IP-адрес пользователя и SIP URI. Подробное описание собираемых данных см. в разделе [Заявление о конфиденциальности Skype для бизнеса ](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx).</span><span class="sxs-lookup"><span data-stu-id="b1c30-p110">Error reporting data may also contain personally identifiable information such as the user's IP address and Session Initiation Protocol Uniform Resource Identifier (SIP URI). See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) for a detailed explanation of what's collected.</span></span>
  
<span data-ttu-id="b1c30-186">Для отчетов об ошибках требуется следующее.</span><span class="sxs-lookup"><span data-stu-id="b1c30-186">Error reporting requires two things:</span></span>
  
- <span data-ttu-id="b1c30-p111">Параметру "Групповая политика DisableAutomaticSendTracing" должно быть присвоено значение False на сервере или в центре администрирования клиента (состояние по умолчанию). Дополнительные сведения см. в разделе [ Настройка политик начальной загрузки клиентов в Skype для бизнеса Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx).</span><span class="sxs-lookup"><span data-stu-id="b1c30-p111">The DisableAutomaticSendTracing Group Policy setting be set to False on the server or in the tenant admin center (this is the default state). See [Configure client bootstrapping policies in Skype for Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) for more information.</span></span>
    
- <span data-ttu-id="b1c30-189">Конечные пользователи делают выбор индивидуально на вкладке "Общие" (щелкните значок шестеренки, откроется диалоговое окно "Параметры" с вкладкой "Общие") в клиенте Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="b1c30-189">End users individually opt in from the General tab (click the gear icon and the Option dialog opens with the General tab displayed) in the Skype for Business client.</span></span>
    
     ![Значок шестеренки](../images/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)
  
![Skype for Business data collection checkbox in the Options > General dialog](../images/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
<span data-ttu-id="b1c30-p112">Для приложения для собраний Skype параметр MeetingUxEnableTelemetry также управляет отчетами об ошибках, а параметры Watson управляют отправкой сведений о нарушениях в работе Windows. В приложении для собраний Skype нет пользовательского параметра, аналогичного тому, который находится в диалоговом окне клиента для настольных ПК.</span><span class="sxs-lookup"><span data-stu-id="b1c30-p112">For Skype Meetings App, the MeetingUxEnableTelemetry also controls error reporting, although for crashes on Windows, the Watson settings control uploading crash info. There is no user setting for Skype Meetings App like you see in the desktop client dialog box.</span></span>
  
<span data-ttu-id="b1c30-194">Дополнительные сведения см. в разделе [Настройка общих параметров в Skype для бизнеса](http://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439).</span><span class="sxs-lookup"><span data-stu-id="b1c30-194">See [Set General options in Skype for Business](http://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) for more information.</span></span>
  
<span data-ttu-id="b1c30-195">Сведения о настройке сети см. в разделе [Настройка сети для Skype для бизнеса Online](http://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66).</span><span class="sxs-lookup"><span data-stu-id="b1c30-195">You can see [Set up your network for Skype for Business Online](http://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) to set up your network.</span></span>
  
<span data-ttu-id="b1c30-196">Для пользователей 21Vianet, использующих Office 365 см. [Set up your network for Lync Online](http://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span><span class="sxs-lookup"><span data-stu-id="b1c30-196">If you are using Office 365 operated by 21Vianet in China, see [Set up your network for Skype for Business Online operated by 21Vianet](http://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b1c30-197">См. также:</span><span class="sxs-lookup"><span data-stu-id="b1c30-197">Related topics</span></span>
[<span data-ttu-id="b1c30-198">Программа улучшения качества программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="b1c30-198">Customer Experience Improvement Program</span></span>](https://www.microsoft.com/products/ceip/en-US/default.mspx)

[<span data-ttu-id="b1c30-199">Доступность страны и региона для конференц-связи аудио и вызов планов</span><span class="sxs-lookup"><span data-stu-id="b1c30-199">Country and region availability for Audio Conferencing and Calling Plans</span></span>](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
