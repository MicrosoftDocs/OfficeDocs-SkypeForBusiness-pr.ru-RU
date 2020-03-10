---
title: Рекомендации по сбору данных
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
hideEdit: true
description: Microsoft collects census, usage, and error data to understand how Skype for Business is being used and where users encounter problems. The data is used to plan product improvements.
ms.openlocfilehash: 1c88086038c3874ae95f6151c1d04d13e0b9ccaf
ms.sourcegitcommit: 33bec766519397f898518a999d358657a413924c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583106"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a><span data-ttu-id="a1628-104">Рекомендации по сбору данных для Skype для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a1628-104">Skype for Business and Microsoft Teams data collection practices</span></span>

<span data-ttu-id="a1628-105">Skype для бизнеса Server и Skype для бизнеса Online, а также приложения Skype для бизнеса и Microsoft Teams, собирают данные, чтобы помочь Microsoft понять, как используются эти продукты и какие типы ошибок, например ошибки при входе, произошел.</span><span class="sxs-lookup"><span data-stu-id="a1628-105">Skype for Business Server and Skype for Business Online, along with Skype for Business and Microsoft Teams apps, collect data to help Microsoft understand how these products are being used and what kinds of errors, such as sign-in errors, have occurred.</span></span> <span data-ttu-id="a1628-106">Эта информация помогает проанализировать шаблоны использования, спланировать новые функции, а также выполнить диагностику и устранение проблемных областей.</span><span class="sxs-lookup"><span data-stu-id="a1628-106">This information helps us understand usage patterns, plan new features, and troubleshoot and fix problem areas.</span></span>

<span data-ttu-id="a1628-p103">Данные об использовании собираются автоматические, все другие данные могут быть собраны только с разрешения администратора и/или пользователя. Сбор данных делится на три категории:</span><span class="sxs-lookup"><span data-stu-id="a1628-p103">While some usage data is collected automatically, other data can only be collected when the admin and/or user chooses to allow it. Data collection falls into these three categories:</span></span>

- <span data-ttu-id="a1628-109">Данные переписи</span><span class="sxs-lookup"><span data-stu-id="a1628-109">Census data</span></span>

- <span data-ttu-id="a1628-110">Данные по использованию</span><span class="sxs-lookup"><span data-stu-id="a1628-110">Usage data</span></span>

- <span data-ttu-id="a1628-111">Предоставляемые отчеты об ошибках</span><span class="sxs-lookup"><span data-stu-id="a1628-111">Error reporting data</span></span>

## <a name="census-data"></a><span data-ttu-id="a1628-112">Данные переписи</span><span class="sxs-lookup"><span data-stu-id="a1628-112">Census data</span></span>

<span data-ttu-id="a1628-113">Переписные данные задаются исключительно для предоставления, поддержки и улучшения Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a1628-113">Census data is acquired solely to provide, support, and improve Skype for Business.</span></span> <span data-ttu-id="a1628-114">Microsoft Teams и Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="a1628-114">Microsoft Teams, and Skype for Business Online.</span></span> <span data-ttu-id="a1628-115">Эти данные включают информацию о среде, например, версии устройства и операционной системы, а также региональные и языковые настройки.</span><span class="sxs-lookup"><span data-stu-id="a1628-115">It includes environmental information such as device and operating system versions, and regional and language settings.</span></span> <span data-ttu-id="a1628-116">Кроме того, они содержат счетчики попыток входа и сбоев.</span><span class="sxs-lookup"><span data-stu-id="a1628-116">It also includes counters for sign-in attempts and failures.</span></span> <span data-ttu-id="a1628-117">Ниже приведены конкретные примеры собранных данных переписи:</span><span class="sxs-lookup"><span data-stu-id="a1628-117">Here are some specific examples of the census data that's collected:</span></span>

|<span data-ttu-id="a1628-118">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="a1628-118">**Data type**</span></span>|<span data-ttu-id="a1628-119">**Пример**</span><span class="sxs-lookup"><span data-stu-id="a1628-119">**Example**</span></span>|<span data-ttu-id="a1628-120">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="a1628-120">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a1628-121">AppName</span><span class="sxs-lookup"><span data-stu-id="a1628-121">AppName</span></span>  <br/> |<span data-ttu-id="a1628-122">ифонескипе</span><span class="sxs-lookup"><span data-stu-id="a1628-122">iPhoneSkype</span></span>  <br/> ||
|<span data-ttu-id="a1628-123">девицемодел</span><span class="sxs-lookup"><span data-stu-id="a1628-123">DeviceModel</span></span>  <br/> |<span data-ttu-id="a1628-124">iPhone</span><span class="sxs-lookup"><span data-stu-id="a1628-124">iPhone</span></span>  <br/> ||
|<span data-ttu-id="a1628-125">Название ОС</span><span class="sxs-lookup"><span data-stu-id="a1628-125">OSName</span></span>  <br/> |<span data-ttu-id="a1628-126">ифонеиос</span><span class="sxs-lookup"><span data-stu-id="a1628-126">iPhoneiOS</span></span>  <br/> ||
|<span data-ttu-id="a1628-127">Версия ОС</span><span class="sxs-lookup"><span data-stu-id="a1628-127">OSVersion</span></span>  <br/> |<span data-ttu-id="a1628-128">8,3</span><span class="sxs-lookup"><span data-stu-id="a1628-128">8.3</span></span>  <br/> ||
|<span data-ttu-id="a1628-129">усерлангуаже</span><span class="sxs-lookup"><span data-stu-id="a1628-129">UserLanguage</span></span>  <br/> |<span data-ttu-id="a1628-130">EN-US</span><span class="sxs-lookup"><span data-stu-id="a1628-130">EN-US</span></span>  <br/> ||
|<span data-ttu-id="a1628-131">Идентификатора пользователя</span><span class="sxs-lookup"><span data-stu-id="a1628-131">UserID</span></span>  <br/> |<span data-ttu-id="a1628-132">E296D735-4F36-4E18-7C3B-52E1A02A0164</span><span class="sxs-lookup"><span data-stu-id="a1628-132">E296D735-4F36-4E18-7C3B-52E1A02A0164</span></span>  <br/> |<span data-ttu-id="a1628-p105">Идентификатор хешируется дважды: первый раз в клиенте и затем в службе телеметрии. Хеширование гарантирует, что идентификатор не может быть связан с конкретным пользователем.</span><span class="sxs-lookup"><span data-stu-id="a1628-p105">The ID is hashed twice: once on the client and again on the telemetry service. The hashing ensures the ID cannot be linked to a specific user.</span></span>  <br/> |
|<span data-ttu-id="a1628-135">Устройства</span><span class="sxs-lookup"><span data-stu-id="a1628-135">DeviceID</span></span>  <br/> |<span data-ttu-id="a1628-136">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span><span class="sxs-lookup"><span data-stu-id="a1628-136">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span></span>  <br/> |<span data-ttu-id="a1628-137">Идентификатор устройства  это глобальный уникальный идентификатор, который единожды генерируется на устройстве случайным образом и отправляется в службу телеметрии.</span><span class="sxs-lookup"><span data-stu-id="a1628-137">The device ID is a GUID that's randomly generated once on the device and sent to the telemetry service.</span></span>  <br/> |

<span data-ttu-id="a1628-p106">Данные переписи НЕ содержат информацию, идентифицирующую организацию или пользователя. Дополнительные сведения см. в разделе [Заявление о конфиденциальности Skype для бизнеса](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx).</span><span class="sxs-lookup"><span data-stu-id="a1628-p106">Census data DOES NOT contain any information that identifies your organization or users. See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for more information.</span></span>

<span data-ttu-id="a1628-140">Данные переписи включены по умолчанию и не могут быть отключены администраторами или пользователями.</span><span class="sxs-lookup"><span data-stu-id="a1628-140">Census data is on by default and cannot be turned off by admins or end users.</span></span>

## <a name="usage-data"></a><span data-ttu-id="a1628-141">Данные по использованию</span><span class="sxs-lookup"><span data-stu-id="a1628-141">Usage data</span></span>

<span data-ttu-id="a1628-142">Данные по использованию содержат такую информацию, как количество совершенных вызов, количество отправленных или полученных сообщений, количество присоединенных собраний, частоту использования функций и проблемы, связанные со стабильностью.</span><span class="sxs-lookup"><span data-stu-id="a1628-142">Usage data includes information such as number of calls made, number of IMs sent or received, number of meetings joined, frequency of features used, and stability issues.</span></span>

<span data-ttu-id="a1628-p107">Данные по использованию могут содержать информацию, идентифицирующую организацию, например, contoso.com. Ниже приведены конкретные примеры собранных данных по использованию:</span><span class="sxs-lookup"><span data-stu-id="a1628-p107">Usage data might contain information that identifies your organization, such as contoso.com. Here are some specific examples of the usage data that's collected:</span></span>

|<span data-ttu-id="a1628-145">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="a1628-145">**Data type**</span></span>|<span data-ttu-id="a1628-146">**Пример**</span><span class="sxs-lookup"><span data-stu-id="a1628-146">**Example**</span></span>|<span data-ttu-id="a1628-147">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="a1628-147">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a1628-148">Отправлено сообщений</span><span class="sxs-lookup"><span data-stu-id="a1628-148">IM Sent</span></span>  <br/> |<span data-ttu-id="a1628-149">12</span><span class="sxs-lookup"><span data-stu-id="a1628-149">12</span></span>  <br/> ||
|<span data-ttu-id="a1628-150">Получено сообщений</span><span class="sxs-lookup"><span data-stu-id="a1628-150">IM Received</span></span>  <br/> |<span data-ttu-id="a1628-151">5</span><span class="sxs-lookup"><span data-stu-id="a1628-151">5</span></span>  <br/> ||
|<span data-ttu-id="a1628-152">Присоединение к собранию (попытки)</span><span class="sxs-lookup"><span data-stu-id="a1628-152">Join a meeting (attempts)</span></span>  <br/> |<span data-ttu-id="a1628-153">5</span><span class="sxs-lookup"><span data-stu-id="a1628-153">5</span></span>  <br/> ||
|<span data-ttu-id="a1628-154">Присоединение к собранию (успешно)</span><span class="sxs-lookup"><span data-stu-id="a1628-154">Join a meeting (success)</span></span>  <br/> |<span data-ttu-id="a1628-155">4</span><span class="sxs-lookup"><span data-stu-id="a1628-155">4</span></span>  <br/> ||
|<span data-ttu-id="a1628-156">Минуты вызовов/собраний</span><span class="sxs-lookup"><span data-stu-id="a1628-156">Call/meeting minutes</span></span>  <br/> |<span data-ttu-id="a1628-157">30 минут</span><span class="sxs-lookup"><span data-stu-id="a1628-157">30 mins</span></span>  <br/> ||
|<span data-ttu-id="a1628-158">федератионпартнер</span><span class="sxs-lookup"><span data-stu-id="a1628-158">FederationPartner</span></span>  <br/> |<span data-ttu-id="a1628-159">Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a1628-159">Microsoft.com</span></span>  <br/> |<span data-ttu-id="a1628-160">Это имя организации, зарегистрированное в Office 365 и переданное в открытом видео, т. е. без затенения.</span><span class="sxs-lookup"><span data-stu-id="a1628-160">This is the name of the organization registered in Office 365 and is transmitted in cleartext, which means it's not obfuscated.</span></span>  <br/> |

<span data-ttu-id="a1628-161">Данные по использованию НЕ содержат информацию, идентифицирующую пользователей.</span><span class="sxs-lookup"><span data-stu-id="a1628-161">Usage data DOES NOT contain any information that identifies users.</span></span>

<span data-ttu-id="a1628-162">Сбор данных об использовании по умолчанию включен, но локальные администраторы могут отключить ее с помощью параметра групповой политики ДисаблеаутоматиксендтраЦинг в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a1628-162">Usage data collection is on by default, but on-premises admins can turn it off using the DisableAutomaticSendTracing Group Policy setting on Skype for Business Server.</span></span> <span data-ttu-id="a1628-163">Отключение этого параметра влияет на всех пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="a1628-163">Turning this setting off affects all users in the organization.</span></span> <span data-ttu-id="a1628-164">Дополнительные сведения приведены в разделе [Настройка политик начальной загрузки клиентов](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) .</span><span class="sxs-lookup"><span data-stu-id="a1628-164">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>

<span data-ttu-id="a1628-165">Конечные пользователи не могут включить или отключить сбор данных.</span><span class="sxs-lookup"><span data-stu-id="a1628-165">End users cannot turn usage data collection on or off.</span></span>

<span data-ttu-id="a1628-166">Управлять телеметрией для веб-страниц приложения для собраний Skype и агента присоединения можно с помощью следующей политики:</span><span class="sxs-lookup"><span data-stu-id="a1628-166">For Skype Meetings App and the join launcher web pages, the way to control telemetry is through this policy:</span></span>

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

<span data-ttu-id="a1628-p109">Для этой политики по умолчанию установлено значение False, поэтому сбор данных телеметрии по умолчанию отключен. Этот параметр задается для каждого пула и позволяет управлять всеми пользователями, которые подключаются к собранию, проводимому на сервере, с помощью приложения для собраний Skype.</span><span class="sxs-lookup"><span data-stu-id="a1628-p109">This policy defaults to false, so telemetry collection is off by default. This setting is per-pool and controls all users who connect with Skype Meetings App to a meeting hosted on that server.</span></span>

## <a name="error-reporting-data"></a><span data-ttu-id="a1628-169">Предоставляемые отчеты об ошибках</span><span class="sxs-lookup"><span data-stu-id="a1628-169">Error reporting data</span></span>

<span data-ttu-id="a1628-p110">Предоставляемые отчеты об ошибках могут содержать информацию о производительности и надежности, конфигурации устройства, качестве сетевого подключения, кодах ошибок, журналах ошибок и исключениях. Ниже приведены конкретные примеры данных, собираемых в отчете об ошибках.</span><span class="sxs-lookup"><span data-stu-id="a1628-p110">Error reporting data can include information about performance and reliability, device configuration, network connection quality, error codes, error logs, and exceptions. Here are some specific examples of error reporting data that's collected:</span></span>

|<span data-ttu-id="a1628-172">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="a1628-172">**Data type**</span></span>|<span data-ttu-id="a1628-173">**Пример**</span><span class="sxs-lookup"><span data-stu-id="a1628-173">**Example**</span></span>|<span data-ttu-id="a1628-174">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="a1628-174">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a1628-175">Направление отправки сообщений</span><span class="sxs-lookup"><span data-stu-id="a1628-175">Message direction</span></span>  <br/> |<span data-ttu-id="a1628-176">Входящие</span><span class="sxs-lookup"><span data-stu-id="a1628-176">Incoming</span></span>  <br/> ||
|<span data-ttu-id="a1628-177">Состояние беседы</span><span class="sxs-lookup"><span data-stu-id="a1628-177">Conversation state</span></span>  <br/> |<span data-ttu-id="a1628-178">Неактивн.</span><span class="sxs-lookup"><span data-stu-id="a1628-178">Idle</span></span>  <br/> ||
|<span data-ttu-id="a1628-179">Идентификатор потока беседы</span><span class="sxs-lookup"><span data-stu-id="a1628-179">Conversation thread ID</span></span>  <br/> |<span data-ttu-id="a1628-180">AdDO8hsJqilU93hQHC3OZaPR2saEA = =</span><span class="sxs-lookup"><span data-stu-id="a1628-180">AdDO8hsJqilU93hQHC3OZaPR2saEA==</span></span>  <br/> ||
|<span data-ttu-id="a1628-181">Идентификатора пользователя</span><span class="sxs-lookup"><span data-stu-id="a1628-181">UserID</span></span>  <br/> |<span data-ttu-id="a1628-182">амосмарбле</span><span class="sxs-lookup"><span data-stu-id="a1628-182">amosmarble</span></span> <br/> |<span data-ttu-id="a1628-183">Идентификатор отправляется в открытом виде, который хэшируется службой телеметрии перед сохранением</span><span class="sxs-lookup"><span data-stu-id="a1628-183">The ID is sent in cleartext , which the telemetry service hashes before storing it</span></span>  <br/> |

<span data-ttu-id="a1628-p111">Сведения, собираемые в отчете об ошибках, содержат личную информацию, включая IP-адрес пользователя и SIP URI. Подробное описание собираемых данных см. в разделе [Заявление о конфиденциальности Skype для бизнеса ](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx).</span><span class="sxs-lookup"><span data-stu-id="a1628-p111">Error reporting data may also contain personally identifiable information such as the user's IP address and Session Initiation Protocol Uniform Resource Identifier (SIP URI). See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for a detailed explanation of what's collected.</span></span>

<span data-ttu-id="a1628-186">Для отчетов об ошибках требуется следующее.</span><span class="sxs-lookup"><span data-stu-id="a1628-186">Error reporting requires two things:</span></span>

- <span data-ttu-id="a1628-187">Для параметра групповой политики ДисаблеаутоматиксендтраЦинг задано значение false на сервере или в центре администрирования клиентов (это состояние по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="a1628-187">The DisableAutomaticSendTracing Group Policy setting is set to False on the server or in the tenant admin center (this is the default state).</span></span> <span data-ttu-id="a1628-188">Дополнительные сведения приведены в разделе [Настройка политик начальной загрузки клиентов](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) .</span><span class="sxs-lookup"><span data-stu-id="a1628-188">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>
    
- <span data-ttu-id="a1628-189">Конечные пользователи по отдельности выводятся на вкладке Общие (щелкните ![значок шестеренки, представляющий шестеренку ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) , а затем откроется диалоговое окно **Параметры** , в котором отображается вкладка **Общие** ) в клиенте Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a1628-189">End users individually opt in from the General tab (click the gear icon ![An icon that represents a gear ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) and then the **Options** dialog opens with the **General** tab displayed) in the Skype for Business client.</span></span>
    
 
![Снимок экрана с флажком "сбор данных" в диалоговом окне "Параметры"](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
<span data-ttu-id="a1628-p113">Для приложения для собраний Skype параметр MeetingUxEnableTelemetry также управляет отчетами об ошибках, а параметры Watson управляют отправкой сведений о нарушениях в работе Windows. В приложении для собраний Skype нет пользовательского параметра, аналогичного тому, который находится в диалоговом окне клиента для настольных ПК.</span><span class="sxs-lookup"><span data-stu-id="a1628-p113">For Skype Meetings App, the MeetingUxEnableTelemetry also controls error reporting, although for crashes on Windows, the Watson settings control uploading crash info. There is no user setting for Skype Meetings App like you see in the desktop client dialog box.</span></span>

<span data-ttu-id="a1628-193">Дополнительные сведения см. в разделе [Настройка общих параметров в Skype для бизнеса](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439).</span><span class="sxs-lookup"><span data-stu-id="a1628-193">See [Set General options in Skype for Business](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) for more information.</span></span>

<span data-ttu-id="a1628-194">Сведения о настройке сети см. в разделе [Настройка сети для Skype для бизнеса Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66).</span><span class="sxs-lookup"><span data-stu-id="a1628-194">You can see [Set up your network for Skype for Business Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) to set up your network.</span></span>

<span data-ttu-id="a1628-195">Для пользователей 21Vianet, использующих Office 365 см. [Set up your network for Lync Online](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span><span class="sxs-lookup"><span data-stu-id="a1628-195">If you are using Office 365 operated by 21Vianet in China, see [Set up your network for Skype for Business Online operated by 21Vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a1628-196">См. также:</span><span class="sxs-lookup"><span data-stu-id="a1628-196">Related topics</span></span>
[<span data-ttu-id="a1628-197">Страны и регионы, для которых доступны аудиоконференции и планы звонков</span><span class="sxs-lookup"><span data-stu-id="a1628-197">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
