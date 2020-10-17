---
title: Принципы сбора данных
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: reference
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Legal
- seo-marvel-mar2020
hideEdit: true
description: Узнайте, как корпорация Майкрософт собирает статистические данные, сведения об использовании и ошибках, чтобы определить особенности использования Teams и Skype для бизнеса и связанные с ними проблемы, а также запланировать улучшение продукта.
ms.openlocfilehash: b7f1f7b63645adfb0cfa0c492a680059ef383402
ms.sourcegitcommit: f5ad0fc5be7201b71da4f13586972831c9961e51
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2020
ms.locfileid: "47651236"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a><span data-ttu-id="912b3-103">Принципы сбора данных в Skype для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="912b3-103">Skype for Business and Microsoft Teams data collection practices</span></span>

<span data-ttu-id="912b3-104">Skype для бизнеса Server и Skype для бизнеса Online, а также приложения Skype для бизнеса и Microsoft Teams собирают данные для корпорации Майкрософт, помогая определить, какие продукты используются и какие типы ошибок возникают (например, ошибки входа).</span><span class="sxs-lookup"><span data-stu-id="912b3-104">Skype for Business Server and Skype for Business Online, along with Skype for Business and Microsoft Teams apps, collect data to help Microsoft understand how these products are being used and what kinds of errors, such as sign-in errors, have occurred.</span></span> <span data-ttu-id="912b3-105">Эта информация помогает проанализировать шаблоны использования, спланировать новые функции, а также выполнить диагностику и устранение проблемных областей.</span><span class="sxs-lookup"><span data-stu-id="912b3-105">This information helps us understand usage patterns, plan new features, and troubleshoot and fix problem areas.</span></span>

<span data-ttu-id="912b3-p102">Данные об использовании собираются автоматические, все другие данные могут быть собраны только с разрешения администратора и/или пользователя. Сбор данных делится на три категории:</span><span class="sxs-lookup"><span data-stu-id="912b3-p102">While some usage data is collected automatically, other data can only be collected when the admin and/or user chooses to allow it. Data collection falls into these three categories:</span></span>

- <span data-ttu-id="912b3-108">Данные переписи</span><span class="sxs-lookup"><span data-stu-id="912b3-108">Census data</span></span>

- <span data-ttu-id="912b3-109">Данные об использовании</span><span class="sxs-lookup"><span data-stu-id="912b3-109">Usage data</span></span>

- <span data-ttu-id="912b3-110">Предоставляемые отчеты об ошибках</span><span class="sxs-lookup"><span data-stu-id="912b3-110">Error reporting data</span></span>

## <a name="census-data"></a><span data-ttu-id="912b3-111">Статистические данные</span><span class="sxs-lookup"><span data-stu-id="912b3-111">Census data</span></span>

<span data-ttu-id="912b3-112">Статистические данные собираются исключительно для предоставления, поддержки и улучшения Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="912b3-112">Census data is acquired solely to provide, support, and improve Skype for Business.</span></span> <span data-ttu-id="912b3-113">Microsoft Teams и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="912b3-113">Microsoft Teams, and Skype for Business Online.</span></span> <span data-ttu-id="912b3-114">Эти данные включают информацию о среде, например, версии устройства и операционной системы, а также региональные и языковые настройки.</span><span class="sxs-lookup"><span data-stu-id="912b3-114">It includes environmental information such as device and operating system versions, and regional and language settings.</span></span> <span data-ttu-id="912b3-115">Кроме того, они содержат счетчики попыток входа и сбоев.</span><span class="sxs-lookup"><span data-stu-id="912b3-115">It also includes counters for sign-in attempts and failures.</span></span> <span data-ttu-id="912b3-116">Ниже приведены конкретные примеры собранных данных переписи:</span><span class="sxs-lookup"><span data-stu-id="912b3-116">Here are some specific examples of the census data that's collected:</span></span>

|<span data-ttu-id="912b3-117">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="912b3-117">**Data type**</span></span>|<span data-ttu-id="912b3-118">**Пример**</span><span class="sxs-lookup"><span data-stu-id="912b3-118">**Example**</span></span>|<span data-ttu-id="912b3-119">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="912b3-119">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="912b3-120">AppName</span><span class="sxs-lookup"><span data-stu-id="912b3-120">AppName</span></span>  <br/> |<span data-ttu-id="912b3-121">iPhoneSkype</span><span class="sxs-lookup"><span data-stu-id="912b3-121">iPhoneSkype</span></span>  <br/> ||
|<span data-ttu-id="912b3-122">DeviceModel</span><span class="sxs-lookup"><span data-stu-id="912b3-122">DeviceModel</span></span>  <br/> |<span data-ttu-id="912b3-123">iPhone</span><span class="sxs-lookup"><span data-stu-id="912b3-123">iPhone</span></span>  <br/> ||
|<span data-ttu-id="912b3-124">Название ОС</span><span class="sxs-lookup"><span data-stu-id="912b3-124">OSName</span></span>  <br/> |<span data-ttu-id="912b3-125">iPhoneiOS</span><span class="sxs-lookup"><span data-stu-id="912b3-125">iPhoneiOS</span></span>  <br/> ||
|<span data-ttu-id="912b3-126">Версия ОС</span><span class="sxs-lookup"><span data-stu-id="912b3-126">OSVersion</span></span>  <br/> |<span data-ttu-id="912b3-127">8.3</span><span class="sxs-lookup"><span data-stu-id="912b3-127">8.3</span></span>  <br/> ||
|<span data-ttu-id="912b3-128">UserLanguage</span><span class="sxs-lookup"><span data-stu-id="912b3-128">UserLanguage</span></span>  <br/> |<span data-ttu-id="912b3-129">EN-US</span><span class="sxs-lookup"><span data-stu-id="912b3-129">EN-US</span></span>  <br/> ||
|<span data-ttu-id="912b3-130">UserID</span><span class="sxs-lookup"><span data-stu-id="912b3-130">UserID</span></span>  <br/> |<span data-ttu-id="912b3-131">E296D735-4F36-4E18-7C3B-52E1A02A0164</span><span class="sxs-lookup"><span data-stu-id="912b3-131">E296D735-4F36-4E18-7C3B-52E1A02A0164</span></span>  <br/> |<span data-ttu-id="912b3-p104">Идентификатор хешируется дважды: первый раз в клиенте и затем в службе телеметрии. Хеширование гарантирует, что идентификатор не может быть связан с конкретным пользователем.</span><span class="sxs-lookup"><span data-stu-id="912b3-p104">The ID is hashed twice: once on the client and again on the telemetry service. The hashing ensures the ID cannot be linked to a specific user.</span></span>  <br/> |
|<span data-ttu-id="912b3-134">DeviceID</span><span class="sxs-lookup"><span data-stu-id="912b3-134">DeviceID</span></span>  <br/> |<span data-ttu-id="912b3-135">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span><span class="sxs-lookup"><span data-stu-id="912b3-135">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span></span>  <br/> |<span data-ttu-id="912b3-136">Идентификатор устройства  это глобальный уникальный идентификатор, который единожды генерируется на устройстве случайным образом и отправляется в службу телеметрии.</span><span class="sxs-lookup"><span data-stu-id="912b3-136">The device ID is a GUID that's randomly generated once on the device and sent to the telemetry service.</span></span>  <br/> |

<span data-ttu-id="912b3-p105">Данные переписи НЕ содержат информацию, идентифицирующую организацию или пользователя. Дополнительные сведения см. в разделе [Заявление о конфиденциальности Skype для бизнеса](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx).</span><span class="sxs-lookup"><span data-stu-id="912b3-p105">Census data DOES NOT contain any information that identifies your organization or users. See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for more information.</span></span>

<span data-ttu-id="912b3-139">Данные переписи включены по умолчанию и не могут быть отключены администраторами или пользователями.</span><span class="sxs-lookup"><span data-stu-id="912b3-139">Census data is on by default and cannot be turned off by admins or end users.</span></span>

## <a name="usage-data"></a><span data-ttu-id="912b3-140">Данные об использовании</span><span class="sxs-lookup"><span data-stu-id="912b3-140">Usage data</span></span>

<span data-ttu-id="912b3-141">Данные по использованию содержат такую информацию, как количество совершенных вызов, количество отправленных или полученных сообщений, количество присоединенных собраний, частоту использования функций и проблемы, связанные со стабильностью.</span><span class="sxs-lookup"><span data-stu-id="912b3-141">Usage data includes information such as number of calls made, number of IMs sent or received, number of meetings joined, frequency of features used, and stability issues.</span></span>

<span data-ttu-id="912b3-p106">Данные по использованию могут содержать информацию, идентифицирующую организацию, например, contoso.com. Ниже приведены конкретные примеры собранных данных по использованию:</span><span class="sxs-lookup"><span data-stu-id="912b3-p106">Usage data might contain information that identifies your organization, such as contoso.com. Here are some specific examples of the usage data that's collected:</span></span>

|<span data-ttu-id="912b3-144">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="912b3-144">**Data type**</span></span>|<span data-ttu-id="912b3-145">**Пример**</span><span class="sxs-lookup"><span data-stu-id="912b3-145">**Example**</span></span>|<span data-ttu-id="912b3-146">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="912b3-146">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="912b3-147">Отправлено сообщений</span><span class="sxs-lookup"><span data-stu-id="912b3-147">IM Sent</span></span>  <br/> |<span data-ttu-id="912b3-148">12</span><span class="sxs-lookup"><span data-stu-id="912b3-148">12</span></span>  <br/> ||
|<span data-ttu-id="912b3-149">Получено сообщений</span><span class="sxs-lookup"><span data-stu-id="912b3-149">IM Received</span></span>  <br/> |<span data-ttu-id="912b3-150">5</span><span class="sxs-lookup"><span data-stu-id="912b3-150">5</span></span>  <br/> ||
|<span data-ttu-id="912b3-151">Присоединение к собранию (попытки)</span><span class="sxs-lookup"><span data-stu-id="912b3-151">Join a meeting (attempts)</span></span>  <br/> |<span data-ttu-id="912b3-152">5</span><span class="sxs-lookup"><span data-stu-id="912b3-152">5</span></span>  <br/> ||
|<span data-ttu-id="912b3-153">Присоединение к собранию (успешно)</span><span class="sxs-lookup"><span data-stu-id="912b3-153">Join a meeting (success)</span></span>  <br/> |<span data-ttu-id="912b3-154">4</span><span class="sxs-lookup"><span data-stu-id="912b3-154">4</span></span>  <br/> ||
|<span data-ttu-id="912b3-155">Минуты вызовов/собраний</span><span class="sxs-lookup"><span data-stu-id="912b3-155">Call/meeting minutes</span></span>  <br/> |<span data-ttu-id="912b3-156">30 минут</span><span class="sxs-lookup"><span data-stu-id="912b3-156">30 mins</span></span>  <br/> ||
|<span data-ttu-id="912b3-157">FederationPartner</span><span class="sxs-lookup"><span data-stu-id="912b3-157">FederationPartner</span></span>  <br/> |<span data-ttu-id="912b3-158">Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="912b3-158">Microsoft.com</span></span>  <br/> |<span data-ttu-id="912b3-159">Это имя организации, зарегистрированное в Office 365 и переданное в открытом видео, т. е. без затенения.</span><span class="sxs-lookup"><span data-stu-id="912b3-159">This is the name of the organization registered in Office 365 and is transmitted in cleartext, which means it's not obfuscated.</span></span>  <br/> |

<span data-ttu-id="912b3-160">Данные по использованию НЕ содержат информацию, идентифицирующую пользователей.</span><span class="sxs-lookup"><span data-stu-id="912b3-160">Usage data DOES NOT contain any information that identifies users.</span></span>

<span data-ttu-id="912b3-161">По умолчанию сбор данных об использовании включен, но локальные администраторы могут отключить его с помощью параметра групповой политики DisableAutomaticSendTracing в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="912b3-161">Usage data collection is on by default, but on-premises admins can turn it off using the DisableAutomaticSendTracing Group Policy setting on Skype for Business Server.</span></span> <span data-ttu-id="912b3-162">Отключение этого параметра затрагивает всех пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="912b3-162">Turning this setting off affects all users in the organization.</span></span> <span data-ttu-id="912b3-163">Дополнительные сведения см. в статье [Настройка политик начальной загрузки клиентов](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies).</span><span class="sxs-lookup"><span data-stu-id="912b3-163">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>

<span data-ttu-id="912b3-164">Конечные пользователи не могут включить или отключить сбор данных.</span><span class="sxs-lookup"><span data-stu-id="912b3-164">End users cannot turn usage data collection on or off.</span></span>

<span data-ttu-id="912b3-165">Управлять телеметрией для веб-страниц приложения для собраний Skype и агента присоединения можно с помощью следующей политики:</span><span class="sxs-lookup"><span data-stu-id="912b3-165">For Skype Meetings App and the join launcher web pages, the way to control telemetry is through this policy:</span></span>

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

<span data-ttu-id="912b3-p108">Для этой политики по умолчанию установлено значение False, поэтому сбор данных телеметрии по умолчанию отключен. Этот параметр задается для каждого пула и позволяет управлять всеми пользователями, которые подключаются к собранию, проводимому на сервере, с помощью приложения для собраний Skype.</span><span class="sxs-lookup"><span data-stu-id="912b3-p108">This policy defaults to false, so telemetry collection is off by default. This setting is per-pool and controls all users who connect with Skype Meetings App to a meeting hosted on that server.</span></span>

## <a name="error-reporting-data"></a><span data-ttu-id="912b3-168">Данные для отчетов об ошибках</span><span class="sxs-lookup"><span data-stu-id="912b3-168">Error reporting data</span></span>

<span data-ttu-id="912b3-p109">Предоставляемые отчеты об ошибках могут содержать информацию о производительности и надежности, конфигурации устройства, качестве сетевого подключения, кодах ошибок, журналах ошибок и исключениях. Ниже приведены конкретные примеры данных, собираемых в отчете об ошибках.</span><span class="sxs-lookup"><span data-stu-id="912b3-p109">Error reporting data can include information about performance and reliability, device configuration, network connection quality, error codes, error logs, and exceptions. Here are some specific examples of error reporting data that's collected:</span></span>

|<span data-ttu-id="912b3-171">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="912b3-171">**Data type**</span></span>|<span data-ttu-id="912b3-172">**Пример**</span><span class="sxs-lookup"><span data-stu-id="912b3-172">**Example**</span></span>|<span data-ttu-id="912b3-173">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="912b3-173">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="912b3-174">Направление отправки сообщений</span><span class="sxs-lookup"><span data-stu-id="912b3-174">Message direction</span></span>  <br/> |<span data-ttu-id="912b3-175">Входящие</span><span class="sxs-lookup"><span data-stu-id="912b3-175">Incoming</span></span>  <br/> ||
|<span data-ttu-id="912b3-176">Состояние беседы</span><span class="sxs-lookup"><span data-stu-id="912b3-176">Conversation state</span></span>  <br/> |<span data-ttu-id="912b3-177">Бездействие</span><span class="sxs-lookup"><span data-stu-id="912b3-177">Idle</span></span>  <br/> ||
|<span data-ttu-id="912b3-178">Идентификатор потока беседы</span><span class="sxs-lookup"><span data-stu-id="912b3-178">Conversation thread ID</span></span>  <br/> |<span data-ttu-id="912b3-179">AdDO8hsJqilU93hQHC3OZaPR2saEA==</span><span class="sxs-lookup"><span data-stu-id="912b3-179">AdDO8hsJqilU93hQHC3OZaPR2saEA==</span></span>  <br/> ||
|<span data-ttu-id="912b3-180">UserID</span><span class="sxs-lookup"><span data-stu-id="912b3-180">UserID</span></span>  <br/> |<span data-ttu-id="912b3-181">amosmarble</span><span class="sxs-lookup"><span data-stu-id="912b3-181">amosmarble</span></span> <br/> |<span data-ttu-id="912b3-182">Идентификатор отправляется в открытом виде, который хэшируется службой телеметрии перед сохранением</span><span class="sxs-lookup"><span data-stu-id="912b3-182">The ID is sent in cleartext , which the telemetry service hashes before storing it</span></span>  <br/> |

<span data-ttu-id="912b3-p110">Сведения, собираемые в отчете об ошибках, содержат личную информацию, включая IP-адрес пользователя и SIP URI. Подробное описание собираемых данных см. в разделе [Заявление о конфиденциальности Skype для бизнеса ](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx).</span><span class="sxs-lookup"><span data-stu-id="912b3-p110">Error reporting data may also contain personally identifiable information such as the user's IP address and Session Initiation Protocol Uniform Resource Identifier (SIP URI). See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for a detailed explanation of what's collected.</span></span>

<span data-ttu-id="912b3-185">Для отчетов об ошибках требуется следующее.</span><span class="sxs-lookup"><span data-stu-id="912b3-185">Error reporting requires two things:</span></span>

- <span data-ttu-id="912b3-186">Для параметра групповой политики DisableAutomaticSendTracing задано значение False на сервере или в центре администрирования клиента (этот вариант выбран по умолчанию.).</span><span class="sxs-lookup"><span data-stu-id="912b3-186">The DisableAutomaticSendTracing Group Policy setting is set to False on the server or in the tenant admin center (this is the default state).</span></span> <span data-ttu-id="912b3-187">Дополнительные сведения см. в статье [Настройка политик начальной загрузки клиентов](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies).</span><span class="sxs-lookup"><span data-stu-id="912b3-187">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>
    
- <span data-ttu-id="912b3-188">Пользователи дают согласие на сбор данных индивидуально на вкладке "Общие" (щелкните значок шестеренки ![Значок в форме шестеренки ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png), и откроется диалоговое окно **Параметры** с вкладкой **Общие**) в клиенте Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="912b3-188">End users individually opt in from the General tab (click the gear icon ![An icon that represents a gear ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) and then the **Options** dialog opens with the **General** tab displayed) in the Skype for Business client.</span></span>
    
 
![Снимок экрана: флажок "Сбор данных" в диалоговом окне "Параметры"](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
<span data-ttu-id="912b3-p112">Для приложения для собраний Skype параметр MeetingUxEnableTelemetry также управляет отчетами об ошибках, а параметры Watson управляют отправкой сведений о нарушениях в работе Windows. В приложении для собраний Skype нет пользовательского параметра, аналогичного тому, который находится в диалоговом окне клиента для настольных ПК.</span><span class="sxs-lookup"><span data-stu-id="912b3-p112">For Skype Meetings App, the MeetingUxEnableTelemetry also controls error reporting, although for crashes on Windows, the Watson settings control uploading crash info. There is no user setting for Skype Meetings App like you see in the desktop client dialog box.</span></span>

<span data-ttu-id="912b3-192">Дополнительные сведения см. в разделе [Настройка общих параметров в Skype для бизнеса](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439).</span><span class="sxs-lookup"><span data-stu-id="912b3-192">See [Set General options in Skype for Business](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) for more information.</span></span>

<span data-ttu-id="912b3-193">Сведения о настройке сети см. в разделе [Настройка сети для Skype для бизнеса Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66).</span><span class="sxs-lookup"><span data-stu-id="912b3-193">You can see [Set up your network for Skype for Business Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) to set up your network.</span></span>

<span data-ttu-id="912b3-194">Если вы используете службу Microsoft 365 или Office 365, предоставляемую 21Vianet в Китае, см. [Настройка сети для Skype для бизнеса Online, предоставляемого 21Vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span><span class="sxs-lookup"><span data-stu-id="912b3-194">If you are using Microsoft 365 or Office 365 operated by 21Vianet in China, see [Set up your network for Skype for Business Online operated by 21Vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span></span>

## <a name="related-topics"></a><span data-ttu-id="912b3-195">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="912b3-195">Related topics</span></span>
[<span data-ttu-id="912b3-196">Доступность аудиоконференций и планов звонков в различных странах и регионах</span><span class="sxs-lookup"><span data-stu-id="912b3-196">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
