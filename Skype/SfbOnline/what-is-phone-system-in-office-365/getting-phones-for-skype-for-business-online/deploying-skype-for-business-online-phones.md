---
title: Развертывание телефонов для приложения Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Познакомьтесь с действиями развертывания для получения микропрограммы, при необходимости обновите ее, назначение лицензий и настройка параметров для Скайп для рабочих телефонов online
ms.openlocfilehash: 04cb3aa17574f56d9069f07a10c1c6ae95f9576d
ms.sourcegitcommit: 3f88e2f1fb4dd84bf6e88e29b89cefeb7a0a954b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "29770365"
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="6a0b0-103">Развертывание телефонов для приложения Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="6a0b0-103">Deploying Skype for Business Online phones</span></span>

<span data-ttu-id="6a0b0-104">[] Это руководство посвящено развертыванию IP-телефонов для приложения Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="6a0b0-p101">Наличие номеров телефонов и возможность совершать голосовые звонки является важнейшим фактором для успешной деятельности любой организации. Пользователи, которым назначены номера телефона, могут совершать голосовые звонки на любые устройства с приложением Skype для бизнеса, включая IP-телефоны, персональные компьютеры и мобильные устройства. Дополнительные сведения об IP-телефонах для приложения Skype для бизнеса см. в статье [Телефоны, поддерживаемые в Skype для бизнеса Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="6a0b0-p101">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business. Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices. You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="6a0b0-108">Процедура развертывания IP-телефонов</span><span class="sxs-lookup"><span data-stu-id="6a0b0-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="6a0b0-109">Шаг 1. Скачайте руководства для администраторов и пользователей телефона, предоставляемые производителем</span><span class="sxs-lookup"><span data-stu-id="6a0b0-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="6a0b0-110">Прежде чем начать, рекомендуется скачать руководства по администрированию и эксплуатации телефона.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="6a0b0-111">Телефоны Polycom: см. [Руководство по развертыванию Polycom](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span><span class="sxs-lookup"><span data-stu-id="6a0b0-111">For Polycom phones, see the [Polycom Deployment Guide](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span></span>
    
- <span data-ttu-id="6a0b0-112">Телефоны Yealink: см. [Yealink Skype for Business HD SIP Phones Solution (Решения на основе SIP-телефонов Skype для бизнеса HD)](http://www.yealink.com/products_top_2.html).</span><span class="sxs-lookup"><span data-stu-id="6a0b0-112">For Yealink phones, see [Yealink Skype for Business HD SIP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="6a0b0-113">Телефоны AudioCodes: см. [Руководство по подготовке Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span><span class="sxs-lookup"><span data-stu-id="6a0b0-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="6a0b0-114">Шаг 2. Убедитесь, что приложение Skype для бизнеса поддерживает приобретаемые или переносимые IP-телефоны и встроенное ПО</span><span class="sxs-lookup"><span data-stu-id="6a0b0-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="6a0b0-p102">Поддерживаемые приложением Skype для бизнеса Online телефоны и встроенное ПО также совместимы со Skype для бизнеса Server, но в обратном направлении это утверждение не всегда верно. Чтобы проверить, поддерживаются ли приобретаемые вами телефоны и встроенное ПО, см. статью [Телефоны, поддерживаемые в Skype для бизнеса Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="6a0b0-p102">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true. To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="6a0b0-117">Шаг 3. Проверка наличия соответствующей версии встроенного ПО и его обновление при необходимости</span><span class="sxs-lookup"><span data-stu-id="6a0b0-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="6a0b0-p103">Проверьте версию ПО на телефонах. Производитель:</span><span class="sxs-lookup"><span data-stu-id="6a0b0-p103">Check the firmware version on your phones. For:</span></span>
  
- <span data-ttu-id="6a0b0-120">**Телефоны Polycom VVX**  выберите **Settings** > **Status** > **Platform** > **Application** > **Main** (Параметры > Состояние > Платформа > Приложение > Основные).</span><span class="sxs-lookup"><span data-stu-id="6a0b0-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="6a0b0-121">**Телефоны Yealink**  выберите пункт **Status** (Состояние) на главном экране телефона.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="6a0b0-122">**Телефоны AudioCodes**  выберите **Menu** > **Device Status** > **Firmware version** (Меню > Состояние устройства > Версия встроенного ПО).</span><span class="sxs-lookup"><span data-stu-id="6a0b0-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6a0b0-p104">Сведения о дистанционном доступе к телефону см. в руководствах по администрированию, предлагаемых производителями. См. ссылки на упоминаемые выше руководства пользователей и руководства по эксплуатации телефона.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-p104">For remote access to phone details, refer to manufacturer administration guides. See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="6a0b0-125">**Телефоны Lync Phone Edition (LPE)**  выберите **Menu** > **System Information** (Меню > Сведения о системе) на начальном экране.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="6a0b0-126">Шаг 4. Рекомендации по обновлению устройства</span><span class="sxs-lookup"><span data-stu-id="6a0b0-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="6a0b0-p105">Во встроенном ПО Polycom версий ниже 5.5.1.X был реализован собственный механизм блокировки устройства, который был заменен реализацией блокировки телефона в Skype для бизнеса. При обновлении телефона, защищенного функцией блокировки устройства, с версии 5.4.X.X до версии 5.5.1.X с блокировкой телефона ПИН-код предыдущей функции не переносился, из-за чего телефон оставался незащищенным. Если у вас включена блокировка устройства, необходимо включить следующий параметр в профиле устройства Polycom, чтобы позволить пользователям определять время обновления (lync.deviceUpdate.popUpSK.enabled=1).</span><span class="sxs-lookup"><span data-stu-id="6a0b0-p105">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock." Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured. Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="6a0b0-p106">Служба Skype для бизнеса управляет обновлением встроенного ПО. Обновление для каждого сертифицированного телефона Skype для бизнеса загружается на сервер обновлений Skype для бизнеса, а на всех устройствах обновление включено по умолчанию. В зависимости от периода неактивности телефона и интервалов опроса на телефоны автоматически загружаются и устанавливаются последние версии сертифицированных сборок. Чтобы отключить обновление устройства, выполните командлет [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) и присвойте параметру _EnableDeviceUpdate_ значение `false`.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-p106">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default. Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![Deploying phones.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="6a0b0-p107">При наличии доступной для скачивания и установки версии встроенного ПО пользователь телефона получает уведомление. Например, в уведомлении на телефоне Polycom пользователю предлагается выполнить одну из двух команд: **Update** (Обновить) или **Postpone** (Отложить).</span><span class="sxs-lookup"><span data-stu-id="6a0b0-p107">When a new firmware is available and ready for download and install, the phone will notify the user. Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span></span>
  
![Deploying phones.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="6a0b0-138">Чтобы обновить встроенное ПО на телефоне Polycom, выберите команду **SwUpdate** (Обновление ПО).</span><span class="sxs-lookup"><span data-stu-id="6a0b0-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![Deploying phones.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="6a0b0-p108">Кроме того, для управления обновлениями встроенного ПО вы можете использовать партнерскую систему подготовки. Сведения о партнерской системе подготовки, включая расширенную настройку телефона, см. в руководствах по администрированию, предлагаемых производителями.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-p108">You can also choose to manage firmware updates using a partner provisioning system. For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="6a0b0-142">Чтобы избежать зацикливания, всегда используйте один центр обновления устройства (обновление по штатному каналу или через сторонний сервер подготовки).</span><span class="sxs-lookup"><span data-stu-id="6a0b0-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="6a0b0-143">Шаг 5. Настройка параметров телефона и инфраструктуры</span><span class="sxs-lookup"><span data-stu-id="6a0b0-143">Step 5 - Configuration and infrastructure phone settings</span></span>

<span data-ttu-id="6a0b0-p109">Для настройки самых распространенных параметров телефона и политик с помощью штатной системы Skype для бизнеса можно использовать командлеты Windows PowerShell. Дополнительные сведения об этих параметрах и политиках см. в разделе [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span><span class="sxs-lookup"><span data-stu-id="6a0b0-p109">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="6a0b0-146">При планировании сетевой инфраструктуры см. статью [Skype Operations Framework (Операционная платформа Skype)](https://www.skypeoperationsframework.com/).</span><span class="sxs-lookup"><span data-stu-id="6a0b0-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="6a0b0-147">Шаг 6. Подготовка телефонов для входа пользователей</span><span class="sxs-lookup"><span data-stu-id="6a0b0-147">Step 6 - Preparing for users to sign in</span></span>

<span data-ttu-id="6a0b0-148">Чтобы дать пользователям возможность успешного входа в Скайп для Online бизнес телефон и выполнения звонков, необходимо убедитесь, что пользователи назначаются правильные лицензии.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-148">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses.</span></span> <span data-ttu-id="6a0b0-149">Необходимо как минимум назначить лицензию телефонной системы и тарифный план.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-149">At a minimum, you will need to assign a Phone System license and a Calling Plan.</span></span> <span data-ttu-id="6a0b0-150">Для получения дополнительной информации см. [Лицензирование надстроек в Skype для бизнеса и Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) и [Назначение лицензий Skype для бизнеса и Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="6a0b0-150">For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
  
<span data-ttu-id="6a0b0-151">Для получения дополнительных сведений о планах звонков см. статью [Что такое планы звонков в Office 365?](/microsoftteams/what-are-calling-plans-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="6a0b0-151">You can find out more about Calling Plans by reading [What are Calling Plans in Office 365?](/microsoftteams/what-are-calling-plans-in-office-365)</span></span>
  
- <span data-ttu-id="6a0b0-152">**Варианты входа**, доступные пользователям Online, перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="6a0b0-153">Телефоны **Polycom VVX 5XX/6XX**:</span><span class="sxs-lookup"><span data-stu-id="6a0b0-153">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Deploying phones.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="6a0b0-155">Телефоны **Yealink T48G/T46G**:</span><span class="sxs-lookup"><span data-stu-id="6a0b0-155">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Yealink phones logon.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="6a0b0-157">Дополнительные сведения о поддерживаемых производителем вариантах входа см. в разделе [Телефоны, поддерживаемые в Skype для бизнеса Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="6a0b0-157">For details on sign-in options supported by the manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="6a0b0-p111">**ИД пользователя**. Для входа в систему телефона пользователи могут ввести назначенные им в организации имя пользователя и пароль с помощью клавиш на телефоне или экранной клавиатуры (если есть). Например, в качестве имени пользователя следует использовать формат имени участника-пользователя, такой как <em>amosm@contoso.com</em>  .</span><span class="sxs-lookup"><span data-stu-id="6a0b0-p111">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like <em>amosm@contoso.com</em>  for their user name.</span></span>
    
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="6a0b0-161">IP-телефоны LPE и партнеров для Skype для бизнеса Online не поддерживают проверку подлинности с помощью ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="6a0b0-162">**С помощью ПК** При Эффективная совместная работа над программного обеспечения Ethernet (BToE) установлен на Компьютере пользователя и включен, пользователи могут войти свои телефоны, используя окно проверки подлинности на их Скайп Windows для бизнес-приложения.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-162">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App.</span></span> <span data-ttu-id="6a0b0-163">Другие сведения содержатся в разделе [шаг 7 (необязательно) — Если у вас есть устройства связывания и эффективная совместная работа через Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) .</span><span class="sxs-lookup"><span data-stu-id="6a0b0-163">See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="6a0b0-p113">Для входа в систему телефона пользователи могут ввести назначенные им в организации имя пользователя и пароль. Например, в качестве имени пользователя следует использовать формат имени участника-пользователя, такой как  <em>amosm@contoso.com</em>  .</span><span class="sxs-lookup"><span data-stu-id="6a0b0-p113">Users are required to use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like  <em>amosm@contoso.com</em>  for their user name.</span></span>
  
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="6a0b0-p114">**Веб-вход**. Это новый способ проверки подлинности для пользователей приложения Online, подразумевающий применение стандартного веб-браузера. В этом случае пользователям предлагается набор инструкций по входу с помощью браузера.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-p114">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser. Users will be provided with a set of instructions to follow when they use a browser to sign in.</span></span>
    
  - <span data-ttu-id="6a0b0-169">Телефоны **Polycom VVX 5XX/6XX**:</span><span class="sxs-lookup"><span data-stu-id="6a0b0-169">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Deploying phones.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="6a0b0-171">Телефоны **Yealink T48G/T46G**:</span><span class="sxs-lookup"><span data-stu-id="6a0b0-171">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Yealink phone logon.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="6a0b0-p115">Срок действия формируемого кода составляет 15 минут. По истечении срока действия кода, в зависимости от модели телефона, необходимо нажать кнопку **Retry** (Повтор) или **OK** для формирования нового.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-p115">The code that is generated will expire in 15 minutes. When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span></span>
    
  - <span data-ttu-id="6a0b0-175">Телефоны **Polycom VVX 5XX/6XX**:</span><span class="sxs-lookup"><span data-stu-id="6a0b0-175">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![PIN code expired.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="6a0b0-177">Телефоны **Yealink T48G/T46G**:</span><span class="sxs-lookup"><span data-stu-id="6a0b0-177">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Yealink phones logon.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="6a0b0-179">В браузере перейдите по адресу, отображаемому на экране телефона, и введите свое имя пользователя Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![Deploying phones.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="6a0b0-181">Введите код, отображаемый на телефоне.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-181">Enter the code shown on the phone.</span></span>
    
     ![Deploying phones.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="6a0b0-183">Убедитесь, что на веб-сайте отображается заголовок « **Сертифицированный телефон Skype для бизнеса** [название производителя телефона]» и нажмите **Continue** (Продолжить).</span><span class="sxs-lookup"><span data-stu-id="6a0b0-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**," and click **Continue**.</span></span>
    
     ![Deploying phones.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="6a0b0-185">Щелкните учетные данные пользователя или выберите **Use another account** (Использовать другую учетную запись):</span><span class="sxs-lookup"><span data-stu-id="6a0b0-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![Deploying phones.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="6a0b0-187">После того, как откроется следующая страница, можно закрыть браузер.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-187">When the following page is displayed, it is safe to close the browser.</span></span>
    
     ![Deploying phones.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="6a0b0-189">Телефоны LPE для Skype для бизнеса Online поддерживают вход только с использованием модема USB.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="6a0b0-190">**Поддерживаемые развертывания**. В следующей таблице показаны поддерживаемые типы проверки подлинности для поддерживаемых на данный момент моделей, включая интеграцию с Exchange, современную проверку подлинности с многофакторной проверкой подлинности (MFA), а также локальную проверку и проверку в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6a0b0-191">**Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="6a0b0-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="6a0b0-192">**Exchange**</span><span class="sxs-lookup"><span data-stu-id="6a0b0-192">**Exchange**</span></span> <br/> |<span data-ttu-id="6a0b0-193">**Метод входа в систему телефона**</span><span class="sxs-lookup"><span data-stu-id="6a0b0-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="6a0b0-194">**Доступ к Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="6a0b0-194">**Skype for Business access**</span></span> <br/> |<span data-ttu-id="6a0b0-195">**Доступ к Exchange с применением современной проверки подлинности с многофакторной проверкой подлинности отключен**</span><span class="sxs-lookup"><span data-stu-id="6a0b0-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="6a0b0-196">**Доступ к Exchange с применением современной проверки подлинности с многофакторной проверкой подлинности включен**</span><span class="sxs-lookup"><span data-stu-id="6a0b0-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="6a0b0-197">В Интернете</span><span class="sxs-lookup"><span data-stu-id="6a0b0-197">Online</span></span>  <br/> |<span data-ttu-id="6a0b0-198">В Интернете</span><span class="sxs-lookup"><span data-stu-id="6a0b0-198">Online</span></span>  <br/> |<span data-ttu-id="6a0b0-199">Веб-вход</span><span class="sxs-lookup"><span data-stu-id="6a0b0-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="6a0b0-200">Да</span><span class="sxs-lookup"><span data-stu-id="6a0b0-200">Yes</span></span>  <br/> |<span data-ttu-id="6a0b0-201">Да</span><span class="sxs-lookup"><span data-stu-id="6a0b0-201">Yes</span></span>  <br/> |<span data-ttu-id="6a0b0-202">Да</span><span class="sxs-lookup"><span data-stu-id="6a0b0-202">Yes</span></span>  <br/> |
|<span data-ttu-id="6a0b0-203">В Интернете</span><span class="sxs-lookup"><span data-stu-id="6a0b0-203">Online</span></span>  <br/> |<span data-ttu-id="6a0b0-204">В Интернете</span><span class="sxs-lookup"><span data-stu-id="6a0b0-204">Online</span></span>  <br/> |<span data-ttu-id="6a0b0-205">Имя пользователя/пароль</span><span class="sxs-lookup"><span data-stu-id="6a0b0-205">Username/Password</span></span>  <br/> |<span data-ttu-id="6a0b0-206">Да</span><span class="sxs-lookup"><span data-stu-id="6a0b0-206">Yes</span></span>  <br/> |<span data-ttu-id="6a0b0-207">Да</span><span class="sxs-lookup"><span data-stu-id="6a0b0-207">Yes</span></span>  <br/> |<span data-ttu-id="6a0b0-208">Нет</span><span class="sxs-lookup"><span data-stu-id="6a0b0-208">No</span></span>  <br/> |
|<span data-ttu-id="6a0b0-209">В Интернете</span><span class="sxs-lookup"><span data-stu-id="6a0b0-209">Online</span></span>  <br/> |<span data-ttu-id="6a0b0-210">Локальная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="6a0b0-210">On-premises</span></span>  <br/> |<span data-ttu-id="6a0b0-211">Веб-вход</span><span class="sxs-lookup"><span data-stu-id="6a0b0-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="6a0b0-212">Да</span><span class="sxs-lookup"><span data-stu-id="6a0b0-212">Yes</span></span>  <br/> |<span data-ttu-id="6a0b0-213">Нет</span><span class="sxs-lookup"><span data-stu-id="6a0b0-213">No</span></span>  <br/> |<span data-ttu-id="6a0b0-214">Нет</span><span class="sxs-lookup"><span data-stu-id="6a0b0-214">No</span></span>  <br/> |
|<span data-ttu-id="6a0b0-215">В Интернете</span><span class="sxs-lookup"><span data-stu-id="6a0b0-215">Online</span></span>  <br/> |<span data-ttu-id="6a0b0-216">Локальная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="6a0b0-216">On-Premises</span></span>  <br/> |<span data-ttu-id="6a0b0-217">Имя пользователя/пароль</span><span class="sxs-lookup"><span data-stu-id="6a0b0-217">Username/Password</span></span>  <br/> |<span data-ttu-id="6a0b0-218">Да</span><span class="sxs-lookup"><span data-stu-id="6a0b0-218">Yes</span></span>  <br/> |<span data-ttu-id="6a0b0-219">Да</span><span class="sxs-lookup"><span data-stu-id="6a0b0-219">Yes</span></span>  <br/> |<span data-ttu-id="6a0b0-220">Нет</span><span class="sxs-lookup"><span data-stu-id="6a0b0-220">No</span></span>  <br/> |
|<span data-ttu-id="6a0b0-221">Локальная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="6a0b0-221">On-premises</span></span>  <br/> |<span data-ttu-id="6a0b0-222">Online/локальная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="6a0b0-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="6a0b0-223">Проверка подлинности с помощью ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="6a0b0-223">PIN Authentication</span></span>  <br/> |<span data-ttu-id="6a0b0-224">Да</span><span class="sxs-lookup"><span data-stu-id="6a0b0-224">Yes</span></span>  <br/> |<span data-ttu-id="6a0b0-225">Нет</span><span class="sxs-lookup"><span data-stu-id="6a0b0-225">No</span></span>  <br/> |<span data-ttu-id="6a0b0-226">Нет</span><span class="sxs-lookup"><span data-stu-id="6a0b0-226">No</span></span>  <br/> |
|<span data-ttu-id="6a0b0-227">Локальная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="6a0b0-227">On-premises</span></span>  <br/> |<span data-ttu-id="6a0b0-228">Online/локальная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="6a0b0-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="6a0b0-229">Имя пользователя/пароль</span><span class="sxs-lookup"><span data-stu-id="6a0b0-229">Username/Password</span></span>  <br/> |<span data-ttu-id="6a0b0-230">Да</span><span class="sxs-lookup"><span data-stu-id="6a0b0-230">Yes</span></span>  <br/> |<span data-ttu-id="6a0b0-231">Да</span><span class="sxs-lookup"><span data-stu-id="6a0b0-231">Yes</span></span>  <br/> |<span data-ttu-id="6a0b0-232">Н/Д</span><span class="sxs-lookup"><span data-stu-id="6a0b0-232">N/A</span></span>  <br/> |
|<span data-ttu-id="6a0b0-233">Локальная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="6a0b0-233">On-premises</span></span>  <br/> |<span data-ttu-id="6a0b0-234">Online/локальная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="6a0b0-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="6a0b0-235">Вход с помощью ПК (BTOE)</span><span class="sxs-lookup"><span data-stu-id="6a0b0-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="6a0b0-236">Да</span><span class="sxs-lookup"><span data-stu-id="6a0b0-236">Yes</span></span>  <br/> |<span data-ttu-id="6a0b0-237">Да</span><span class="sxs-lookup"><span data-stu-id="6a0b0-237">Yes</span></span>  <br/> |<span data-ttu-id="6a0b0-238">Н/Д</span><span class="sxs-lookup"><span data-stu-id="6a0b0-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="6a0b0-239">**Функции телефона** Доступный набор функций может незначительно изменяться в зависимости от партнера по программе IP-телефонии.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-239">**Phone features** The feature set may vary slightly based on the IP phone partner.</span></span> <span data-ttu-id="6a0b0-240">Для завершения функции задайте и Дополнительные сведения по вопросам компонентов для каждого производителя телефона можно [телефонах начало для Скайп для бизнеса в Интернет](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="6a0b0-240">For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="6a0b0-p117">**Блокировка телефона**. Это новая функция, используемая для защиты сертифицированных телефонов Skype для бизнеса. Если она включена, после успешной проверки подлинности пользователю предлагается создать ПИН-код. Созданный ПИН-код используется для блокировки телефона по истечении установленного времени ожидания в режиме простоя. Кроме того, блокировка телефона может осуществляться пользователями вручную или синхронно с блокировкой ПК с помощью функции сопряжения с телефоном. Если ПИН-код для блокировки телефона неверно введен несколько раз, осуществляется принудительный выход пользователя из системы телефона, либо телефон блокируется и может быть разблокирован только с помощью кода администратора (реализация зависит от партнера по программе IP-телефонии). ПИН-код пользователя должен содержать от 6 до 15 цифр.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-p117">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone. If enabled, users will be asked to create a PIN upon successful authentication. Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing. If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner. The user's PIN should be between 6 and 15 digits.</span></span>
    
    <span data-ttu-id="6a0b0-246">Отключение блокировки телефона для вашей организации (который устанавливается по умолчанию), измените простоя timeout и выберите, будет ли пользователи могут вносить телефонных звонков во время входящей пропускной способности параметры блокировки или не с использованием.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-246">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings.</span></span> <span data-ttu-id="6a0b0-247">Для получения дополнительных сведений о этих параметров в разделе [Set-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/mt629497.aspx) .</span><span class="sxs-lookup"><span data-stu-id="6a0b0-247">See [Set-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/mt629497.aspx) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="6a0b0-248">Шаг 7 (необязательно). Сопряжение устройств и ПО Better Together over Ethernet (BToE)</span><span class="sxs-lookup"><span data-stu-id="6a0b0-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="6a0b0-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="6a0b0-249"><a name="BK_BTOE"> </a></span></span>

<span data-ttu-id="6a0b0-p119">BToE  это механизм для партнеров по программе IP-телефонии, обеспечивающий сопряжение телефона пользователя с приложением Skype для бизнеса в Windows. Возможности ПО BToE.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-p119">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app. BToE enables users to:</span></span>
  
- <span data-ttu-id="6a0b0-252">Вход пользователя в систему IP-телефона с помощью классического приложения Skype для бизнеса (с помощью ПК).</span><span class="sxs-lookup"><span data-stu-id="6a0b0-252">Sign in to their IP phone using their Skype for Business desktop app (using a PC)</span></span>
    
- <span data-ttu-id="6a0b0-253">Синхронизация функций блокировки телефона и ПК.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-253">Synchronize Phone-Lock with PC lock</span></span>
    
- <span data-ttu-id="6a0b0-254">Звонок щелчком.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-254">Click to call</span></span>
    
<span data-ttu-id="6a0b0-p120">ПО BToE можно настроить для работы в двух режимах:  *Auto*  (Авто) (по умолчанию) и *Manual*  (Ручной). Кроме того, эту функцию можно включить (по умолчанию) или отключить для пользователей с помощью штатных настроек Skype для бизнеса. При работе в режиме *Manual*  (Ручной) для сопряжения телефона с приложением Windows пользователям необходимо выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-p120">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  . It can also be enabled (default)/disabled for users using Skype for Business in-band settings. When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="6a0b0-258">**Развертывание ПО BToE для пользователей**</span><span class="sxs-lookup"><span data-stu-id="6a0b0-258">**To deploy BToE to users**</span></span>
  
1. <span data-ttu-id="6a0b0-259">Подключите телефон к порту ПК.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![Deploying phones.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="6a0b0-p121">Скачайте и установите последнюю версию ПО BToE с веб-сайта производителя по следующим ссылкам. Для удобства рекомендуется распространять и устанавливать ПО BToE с помощью административного решения, такого как System Center Configuration Manager (SCCM). Дополнительные сведения о работе с решением SCCM см. в разделе [Пакеты и программы в System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="6a0b0-p121">Download and install the latest BToE software from the manufacturer website from the links below. For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as System Center Configuration Manager (SCCM). For help using SCCM, See [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span></span>
    
   - [<span data-ttu-id="6a0b0-264">Сайт для скачивания ПО BToE для Polycom:</span><span class="sxs-lookup"><span data-stu-id="6a0b0-264">Polycom BToE Software Download site</span></span>](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [<span data-ttu-id="6a0b0-265">Скачать ПО BToE для Yealink</span><span class="sxs-lookup"><span data-stu-id="6a0b0-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
   - [<span data-ttu-id="6a0b0-266">Скачать ПО BToE для AudioCodes</span><span class="sxs-lookup"><span data-stu-id="6a0b0-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="6a0b0-267">Параметр server для BToE имеет значение **Enabled** и **Автоматический режим** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-267">The server setting for BToE is set to **Enabled** and **Auto mode** by default.</span></span> <span data-ttu-id="6a0b0-268">Дополнительные сведения об изменении этих параметров см. в статье [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span><span class="sxs-lookup"><span data-stu-id="6a0b0-268">To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span></span>
    
> [!NOTE]
> <span data-ttu-id="6a0b0-269">На данный момент ПО BToE не поддерживается на платформах Mac и VDI.</span><span class="sxs-lookup"><span data-stu-id="6a0b0-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="6a0b0-270">См. также:</span><span class="sxs-lookup"><span data-stu-id="6a0b0-270">Related topics</span></span>
[<span data-ttu-id="6a0b0-271">Получение номеров телефонов служб для Skype для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6a0b0-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[<span data-ttu-id="6a0b0-272">Преимущества телефонной системы в Office 365</span><span class="sxs-lookup"><span data-stu-id="6a0b0-272">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="6a0b0-273">Страны и регионы, для которых доступны аудиоконференции и планы звонков</span><span class="sxs-lookup"><span data-stu-id="6a0b0-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
