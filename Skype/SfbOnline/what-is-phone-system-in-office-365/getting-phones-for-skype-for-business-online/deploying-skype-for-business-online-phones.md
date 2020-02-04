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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: Ознакомьтесь с инструкциями по развертыванию, чтобы получить подходящую версию встроенного по, при необходимости обновите ее, назначьте лицензии и настройте параметры для телефонов Skype для бизнеса Online
ms.openlocfilehash: 5eda8c9e21ed93b09b9033c5b70bb359894330f7
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705814"
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="f6880-103">Развертывание телефонов для приложения Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="f6880-103">Deploying Skype for Business Online phones</span></span>

<span data-ttu-id="f6880-104">[] Это руководство посвящено развертыванию IP-телефонов для приложения Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="f6880-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="f6880-p101">Наличие номеров телефонов и возможность совершать голосовые звонки является важнейшим фактором для успешной деятельности любой организации. Пользователи, которым назначены номера телефона, могут совершать голосовые звонки на любые устройства с приложением Skype для бизнеса, включая IP-телефоны, персональные компьютеры и мобильные устройства. Дополнительные сведения об IP-телефонах для приложения Skype для бизнеса см. в статье [Телефоны, поддерживаемые в Skype для бизнеса Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="f6880-p101">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business. Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices. You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="f6880-108">Процедура развертывания IP-телефонов</span><span class="sxs-lookup"><span data-stu-id="f6880-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="f6880-109">Шаг 1. Скачайте руководства для администраторов и пользователей телефона, предоставляемые производителем</span><span class="sxs-lookup"><span data-stu-id="f6880-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="f6880-110">Прежде чем начать, рекомендуется скачать руководства по администрированию и эксплуатации телефона.</span><span class="sxs-lookup"><span data-stu-id="f6880-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="f6880-111">Телефоны Polycom: см. [Руководство по развертыванию Polycom](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span><span class="sxs-lookup"><span data-stu-id="f6880-111">For Polycom phones, see the [Polycom Deployment Guide](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span></span>
    
- <span data-ttu-id="f6880-112">Телефоны Yealink: см. [Yealink Skype for Business HD SIP Phones Solution (Решения на основе SIP-телефонов Skype для бизнеса HD)](http://www.yealink.com/products_top_2.html).</span><span class="sxs-lookup"><span data-stu-id="f6880-112">For Yealink phones, see [Yealink Skype for Business HD SIP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="f6880-113">Телефоны AudioCodes: см. [Руководство по подготовке Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span><span class="sxs-lookup"><span data-stu-id="f6880-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="f6880-114">Шаг 2. Убедитесь, что приложение Skype для бизнеса поддерживает приобретаемые или переносимые IP-телефоны и встроенное ПО</span><span class="sxs-lookup"><span data-stu-id="f6880-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="f6880-p102">Поддерживаемые приложением Skype для бизнеса Online телефоны и встроенное ПО также совместимы со Skype для бизнеса Server, но в обратном направлении это утверждение не всегда верно. Чтобы проверить, поддерживаются ли приобретаемые вами телефоны и встроенное ПО, см. статью [Телефоны, поддерживаемые в Skype для бизнеса Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="f6880-p102">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true. To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="f6880-117">Шаг 3. Проверка наличия соответствующей версии встроенного ПО и его обновление при необходимости</span><span class="sxs-lookup"><span data-stu-id="f6880-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="f6880-p103">Проверьте версию ПО на телефонах. Производитель:</span><span class="sxs-lookup"><span data-stu-id="f6880-p103">Check the firmware version on your phones. For:</span></span>
  
- <span data-ttu-id="f6880-120">**Телефоны Polycom VVX**  выберите **Settings** > **Status** > **Platform** > **Application** > **Main** (Параметры > Состояние > Платформа > Приложение > Основные).</span><span class="sxs-lookup"><span data-stu-id="f6880-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="f6880-121">**Телефоны Yealink**  выберите пункт **Status** (Состояние) на главном экране телефона.</span><span class="sxs-lookup"><span data-stu-id="f6880-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="f6880-122">**Телефоны AudioCodes**  выберите **Menu** > **Device Status** > **Firmware version** (Меню > Состояние устройства > Версия встроенного ПО).</span><span class="sxs-lookup"><span data-stu-id="f6880-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f6880-p104">Сведения о дистанционном доступе к телефону см. в руководствах по администрированию, предлагаемых производителями. См. ссылки на упоминаемые выше руководства пользователей и руководства по эксплуатации телефона.</span><span class="sxs-lookup"><span data-stu-id="f6880-p104">For remote access to phone details, refer to manufacturer administration guides. See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="f6880-125">**Телефоны Lync Phone Edition (LPE)**  выберите **Menu** > **System Information** (Меню > Сведения о системе) на начальном экране.</span><span class="sxs-lookup"><span data-stu-id="f6880-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="f6880-126">Шаг 4. Рекомендации по обновлению устройства</span><span class="sxs-lookup"><span data-stu-id="f6880-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="f6880-p105">Во встроенном ПО Polycom версий ниже 5.5.1.X был реализован собственный механизм блокировки устройства, который был заменен реализацией блокировки телефона в Skype для бизнеса. При обновлении телефона, защищенного функцией блокировки устройства, с версии 5.4.X.X до версии 5.5.1.X с блокировкой телефона ПИН-код предыдущей функции не переносился, из-за чего телефон оставался незащищенным. Если у вас включена блокировка устройства, необходимо включить следующий параметр в профиле устройства Polycom, чтобы позволить пользователям определять время обновления (lync.deviceUpdate.popUpSK.enabled=1).</span><span class="sxs-lookup"><span data-stu-id="f6880-p105">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock." Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured. Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="f6880-p106">Служба Skype для бизнеса управляет обновлением встроенного ПО. Обновление для каждого сертифицированного телефона Skype для бизнеса загружается на сервер обновлений Skype для бизнеса, а на всех устройствах обновление включено по умолчанию. В зависимости от периода неактивности телефона и интервалов опроса на телефоны автоматически загружаются и устанавливаются последние версии сертифицированных сборок. Чтобы отключить обновление устройства, выполните командлет [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) и присвойте параметру _EnableDeviceUpdate_ значение `false`.</span><span class="sxs-lookup"><span data-stu-id="f6880-p106">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default. Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![Снимок экрана, демонстрирующий развертывание телефонов](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="f6880-p107">При наличии доступной для скачивания и установки версии встроенного ПО пользователь телефона получает уведомление. Например, в уведомлении на телефоне Polycom пользователю предлагается выполнить одну из двух команд: **Update** (Обновить) или **Postpone** (Отложить).</span><span class="sxs-lookup"><span data-stu-id="f6880-p107">When a new firmware is available and ready for download and install, the phone will notify the user. Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span></span>
  
![Снимок экрана, на котором показаны параметры обновления и откладывание.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="f6880-138">Чтобы обновить встроенное ПО на телефоне Polycom, выберите команду **SwUpdate** (Обновление ПО).</span><span class="sxs-lookup"><span data-stu-id="f6880-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![Снимок экрана, на котором показан параметр Свупдате](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="f6880-p108">Кроме того, для управления обновлениями встроенного ПО вы можете использовать партнерскую систему подготовки. Сведения о партнерской системе подготовки, включая расширенную настройку телефона, см. в руководствах по администрированию, предлагаемых производителями.</span><span class="sxs-lookup"><span data-stu-id="f6880-p108">You can also choose to manage firmware updates using a partner provisioning system. For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="f6880-142">Чтобы избежать зацикливания, всегда используйте один центр обновления устройства (обновление по штатному каналу или через сторонний сервер подготовки).</span><span class="sxs-lookup"><span data-stu-id="f6880-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="f6880-143">Шаг 5. Настройка параметров телефона и инфраструктуры</span><span class="sxs-lookup"><span data-stu-id="f6880-143">Step 5 - Configuration and infrastructure phone settings</span></span>

<span data-ttu-id="f6880-p109">Для настройки самых распространенных параметров телефона и политик с помощью штатной системы Skype для бизнеса можно использовать командлеты Windows PowerShell. Дополнительные сведения об этих параметрах и политиках см. в разделе [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx).</span><span class="sxs-lookup"><span data-stu-id="f6880-p109">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="f6880-146">При планировании сетевой инфраструктуры см. статью [Skype Operations Framework (Операционная платформа Skype)](https://www.skypeoperationsframework.com/).</span><span class="sxs-lookup"><span data-stu-id="f6880-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="f6880-147">Шаг 6. Подготовка телефонов для входа пользователей</span><span class="sxs-lookup"><span data-stu-id="f6880-147">Step 6 - Preparing for users to sign in</span></span>

<span data-ttu-id="f6880-p110">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses. At a minimum, you will need to assign a Phone System license and a Calling Plan. For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="f6880-p110">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses. At a minimum, you will need to assign a Phone System license and a Calling Plan. For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
  
<span data-ttu-id="f6880-151">Дополнительные сведения о тарифных планах можно найти в статье о тарифах на [телефонную систему и планы звонков](/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="f6880-151">You can find out more about Calling Plans by reading [Phone System and Calling Plans](/microsoftteams/calling-plan-landing-page)</span></span>
  
- <span data-ttu-id="f6880-152">**Варианты входа**, доступные пользователям Online, перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="f6880-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="f6880-153">Телефоны **Polycom VVX 5XX/6XX**:</span><span class="sxs-lookup"><span data-stu-id="f6880-153">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Снимок экрана, на котором показан вход на телефон Polycom](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="f6880-155">Телефоны **Yealink T48G/T46G**:</span><span class="sxs-lookup"><span data-stu-id="f6880-155">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Снимок экрана, на котором показан вход на Yealink телефонов.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="f6880-157">Дополнительные сведения о поддерживаемых производителем вариантах входа см. в разделе [Телефоны, поддерживаемые в Skype для бизнеса Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="f6880-157">For details on sign-in options supported by the manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="f6880-p111">**ИД пользователя**. Для входа в систему телефона пользователи могут ввести назначенные им в организации имя пользователя и пароль с помощью клавиш на телефоне или экранной клавиатуры (если есть). Например, в качестве имени пользователя следует использовать формат имени участника-пользователя, такой как <em>amosm@contoso.com</em>  .</span><span class="sxs-lookup"><span data-stu-id="f6880-p111">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like <em>amosm@contoso.com</em>  for their user name.</span></span>
    
     ![Снимок экрана, на котором показан экран входа](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="f6880-161">IP-телефоны LPE и партнеров для Skype для бизнеса Online не поддерживают проверку подлинности с помощью ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="f6880-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="f6880-p112">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App. See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span><span class="sxs-lookup"><span data-stu-id="f6880-p112">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App. See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="f6880-p113">Для входа в систему телефона пользователи могут ввести назначенные им в организации имя пользователя и пароль. Например, в качестве имени пользователя следует использовать формат имени участника-пользователя, такой как  <em>amosm@contoso.com</em>  .</span><span class="sxs-lookup"><span data-stu-id="f6880-p113">Users are required to use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like  <em>amosm@contoso.com</em>  for their user name.</span></span>
  
     ![Снимок экрана, на котором показан экран входа](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="f6880-p114">**Веб-вход**. Это новый способ проверки подлинности для пользователей приложения Online, подразумевающий применение стандартного веб-браузера. В этом случае пользователям предлагается набор инструкций по входу с помощью браузера.</span><span class="sxs-lookup"><span data-stu-id="f6880-p114">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser. Users will be provided with a set of instructions to follow when they use a browser to sign in.</span></span>
    
  - <span data-ttu-id="f6880-169">Телефоны **Polycom VVX 5XX/6XX**:</span><span class="sxs-lookup"><span data-stu-id="f6880-169">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Снимок экрана, на котором показаны инструкции Polycom](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="f6880-171">Телефоны **Yealink T48G/T46G**:</span><span class="sxs-lookup"><span data-stu-id="f6880-171">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Снимок экрана, на котором показаны инструкции Yealink](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="f6880-p115">Срок действия формируемого кода составляет 15 минут. По истечении срока действия кода, в зависимости от модели телефона, необходимо нажать кнопку **Retry** (Повтор) или **OK** для формирования нового.</span><span class="sxs-lookup"><span data-stu-id="f6880-p115">The code that is generated will expire in 15 minutes. When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span></span>
    
  - <span data-ttu-id="f6880-175">Телефоны **Polycom VVX 5XX/6XX**:</span><span class="sxs-lookup"><span data-stu-id="f6880-175">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Снимок экрана, демонстрирующий Polycom код с истекшим сроком действия](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="f6880-177">Телефоны **Yealink T48G/T46G**:</span><span class="sxs-lookup"><span data-stu-id="f6880-177">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Снимок экрана, демонстрирующий Yealink код с истекшим сроком действия](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="f6880-179">В браузере перейдите по адресу, отображаемому на экране телефона, и введите свое имя пользователя Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="f6880-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![Снимок экрана, на котором показана проверка электронной почты](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="f6880-181">Введите код, отображаемый на телефоне.</span><span class="sxs-lookup"><span data-stu-id="f6880-181">Enter the code shown on the phone.</span></span>
    
     ![Снимок экрана, на котором показано, как ввести код на экране входа](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="f6880-183">Убедитесь, что на веб-сайте отображается заголовок « **Сертифицированный телефон Skype для бизнеса** [название производителя телефона]» и нажмите **Continue** (Продолжить).</span><span class="sxs-lookup"><span data-stu-id="f6880-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**," and click **Continue**.</span></span>
    
     ![Снимок экрана, на котором показана проверка имени](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="f6880-185">Щелкните учетные данные пользователя или выберите **Use another account** (Использовать другую учетную запись):</span><span class="sxs-lookup"><span data-stu-id="f6880-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![Снимок экрана, на котором показаны параметры учетных данных](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="f6880-187">После того, как откроется следующая страница, можно закрыть браузер.</span><span class="sxs-lookup"><span data-stu-id="f6880-187">When the following page is displayed, it is safe to close the browser.</span></span>
    
     ![Снимок экрана, на котором показано сообщение с запросом подтверждения](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="f6880-189">Телефоны LPE для Skype для бизнеса Online поддерживают вход только с использованием модема USB.</span><span class="sxs-lookup"><span data-stu-id="f6880-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="f6880-190">**Поддерживаемые развертывания**. В следующей таблице показаны поддерживаемые типы проверки подлинности для поддерживаемых на данный момент моделей, включая интеграцию с Exchange, современную проверку подлинности с многофакторной проверкой подлинности (MFA), а также локальную проверку и проверку в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="f6880-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f6880-191">**Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="f6880-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="f6880-192">**Exchange**</span><span class="sxs-lookup"><span data-stu-id="f6880-192">**Exchange**</span></span> <br/> |<span data-ttu-id="f6880-193">**Метод входа в систему телефона**</span><span class="sxs-lookup"><span data-stu-id="f6880-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="f6880-194">**Доступ к Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="f6880-194">**Skype for Business access**</span></span> <br/> |<span data-ttu-id="f6880-195">**Доступ к Exchange с применением современной проверки подлинности с многофакторной проверкой подлинности отключен**</span><span class="sxs-lookup"><span data-stu-id="f6880-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="f6880-196">**Доступ к Exchange с применением современной проверки подлинности с многофакторной проверкой подлинности включен**</span><span class="sxs-lookup"><span data-stu-id="f6880-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="f6880-197">В Интернете</span><span class="sxs-lookup"><span data-stu-id="f6880-197">Online</span></span>  <br/> |<span data-ttu-id="f6880-198">В Интернете</span><span class="sxs-lookup"><span data-stu-id="f6880-198">Online</span></span>  <br/> |<span data-ttu-id="f6880-199">Веб-вход</span><span class="sxs-lookup"><span data-stu-id="f6880-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="f6880-200">Да</span><span class="sxs-lookup"><span data-stu-id="f6880-200">Yes</span></span>  <br/> |<span data-ttu-id="f6880-201">Да</span><span class="sxs-lookup"><span data-stu-id="f6880-201">Yes</span></span>  <br/> |<span data-ttu-id="f6880-202">Да</span><span class="sxs-lookup"><span data-stu-id="f6880-202">Yes</span></span>  <br/> |
|<span data-ttu-id="f6880-203">В Интернете</span><span class="sxs-lookup"><span data-stu-id="f6880-203">Online</span></span>  <br/> |<span data-ttu-id="f6880-204">В Интернете</span><span class="sxs-lookup"><span data-stu-id="f6880-204">Online</span></span>  <br/> |<span data-ttu-id="f6880-205">Имя пользователя/пароль</span><span class="sxs-lookup"><span data-stu-id="f6880-205">Username/Password</span></span>  <br/> |<span data-ttu-id="f6880-206">Да</span><span class="sxs-lookup"><span data-stu-id="f6880-206">Yes</span></span>  <br/> |<span data-ttu-id="f6880-207">Да</span><span class="sxs-lookup"><span data-stu-id="f6880-207">Yes</span></span>  <br/> |<span data-ttu-id="f6880-208">Нет</span><span class="sxs-lookup"><span data-stu-id="f6880-208">No</span></span>  <br/> |
|<span data-ttu-id="f6880-209">В Интернете</span><span class="sxs-lookup"><span data-stu-id="f6880-209">Online</span></span>  <br/> |<span data-ttu-id="f6880-210">Локальная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="f6880-210">On-premises</span></span>  <br/> |<span data-ttu-id="f6880-211">Веб-вход</span><span class="sxs-lookup"><span data-stu-id="f6880-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="f6880-212">Да</span><span class="sxs-lookup"><span data-stu-id="f6880-212">Yes</span></span>  <br/> |<span data-ttu-id="f6880-213">Нет</span><span class="sxs-lookup"><span data-stu-id="f6880-213">No</span></span>  <br/> |<span data-ttu-id="f6880-214">Нет</span><span class="sxs-lookup"><span data-stu-id="f6880-214">No</span></span>  <br/> |
|<span data-ttu-id="f6880-215">В Интернете</span><span class="sxs-lookup"><span data-stu-id="f6880-215">Online</span></span>  <br/> |<span data-ttu-id="f6880-216">Локальная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="f6880-216">On-Premises</span></span>  <br/> |<span data-ttu-id="f6880-217">Имя пользователя/пароль</span><span class="sxs-lookup"><span data-stu-id="f6880-217">Username/Password</span></span>  <br/> |<span data-ttu-id="f6880-218">Да</span><span class="sxs-lookup"><span data-stu-id="f6880-218">Yes</span></span>  <br/> |<span data-ttu-id="f6880-219">Да</span><span class="sxs-lookup"><span data-stu-id="f6880-219">Yes</span></span>  <br/> |<span data-ttu-id="f6880-220">Нет</span><span class="sxs-lookup"><span data-stu-id="f6880-220">No</span></span>  <br/> |
|<span data-ttu-id="f6880-221">Локальная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="f6880-221">On-premises</span></span>  <br/> |<span data-ttu-id="f6880-222">Online/локальная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="f6880-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="f6880-223">Проверка подлинности с помощью ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="f6880-223">PIN Authentication</span></span>  <br/> |<span data-ttu-id="f6880-224">Да</span><span class="sxs-lookup"><span data-stu-id="f6880-224">Yes</span></span>  <br/> |<span data-ttu-id="f6880-225">Нет</span><span class="sxs-lookup"><span data-stu-id="f6880-225">No</span></span>  <br/> |<span data-ttu-id="f6880-226">Нет</span><span class="sxs-lookup"><span data-stu-id="f6880-226">No</span></span>  <br/> |
|<span data-ttu-id="f6880-227">Локальная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="f6880-227">On-premises</span></span>  <br/> |<span data-ttu-id="f6880-228">Online/локальная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="f6880-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="f6880-229">Имя пользователя/пароль</span><span class="sxs-lookup"><span data-stu-id="f6880-229">Username/Password</span></span>  <br/> |<span data-ttu-id="f6880-230">Да</span><span class="sxs-lookup"><span data-stu-id="f6880-230">Yes</span></span>  <br/> |<span data-ttu-id="f6880-231">Да</span><span class="sxs-lookup"><span data-stu-id="f6880-231">Yes</span></span>  <br/> |<span data-ttu-id="f6880-232">Н/Д</span><span class="sxs-lookup"><span data-stu-id="f6880-232">N/A</span></span>  <br/> |
|<span data-ttu-id="f6880-233">Локальная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="f6880-233">On-premises</span></span>  <br/> |<span data-ttu-id="f6880-234">Online/локальная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="f6880-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="f6880-235">Вход с помощью ПК (BTOE)</span><span class="sxs-lookup"><span data-stu-id="f6880-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="f6880-236">Да</span><span class="sxs-lookup"><span data-stu-id="f6880-236">Yes</span></span>  <br/> |<span data-ttu-id="f6880-237">Да</span><span class="sxs-lookup"><span data-stu-id="f6880-237">Yes</span></span>  <br/> |<span data-ttu-id="f6880-238">Н/Д</span><span class="sxs-lookup"><span data-stu-id="f6880-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="f6880-p116">**Phone features** The feature set may vary slightly based on the IP phone partner. For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="f6880-p116">**Phone features** The feature set may vary slightly based on the IP phone partner. For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="f6880-p117">**Блокировка телефона**. Это новая функция, используемая для защиты сертифицированных телефонов Skype для бизнеса. Если она включена, после успешной проверки подлинности пользователю предлагается создать ПИН-код. Созданный ПИН-код используется для блокировки телефона по истечении установленного времени ожидания в режиме простоя. Кроме того, блокировка телефона может осуществляться пользователями вручную или синхронно с блокировкой ПК с помощью функции сопряжения с телефоном. Если ПИН-код для блокировки телефона неверно введен несколько раз, осуществляется принудительный выход пользователя из системы телефона, либо телефон блокируется и может быть разблокирован только с помощью кода администратора (реализация зависит от партнера по программе IP-телефонии). ПИН-код пользователя должен содержать от 6 до 15 цифр.</span><span class="sxs-lookup"><span data-stu-id="f6880-p117">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone. If enabled, users will be asked to create a PIN upon successful authentication. Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing. If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner. The user's PIN should be between 6 and 15 digits.</span></span>
    
    <span data-ttu-id="f6880-p118">Вы можете отключить блокировку телефона для своей организации (которая включена по умолчанию), изменить время ожидания простоя и указать, могут ли пользователи совершать телефонные звонки, пока они заблокированы, или не используют параметры настройки. Подробнее об этих параметрах смотрите в разделе [Set-ксукфонеконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f6880-p118">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings. See [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="f6880-248">Шаг 7 (необязательно). Сопряжение устройств и ПО Better Together over Ethernet (BToE)</span><span class="sxs-lookup"><span data-stu-id="f6880-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="f6880-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="f6880-249"><a name="BK_BTOE"> </a></span></span>

<span data-ttu-id="f6880-p119">BToE  это механизм для партнеров по программе IP-телефонии, обеспечивающий сопряжение телефона пользователя с приложением Skype для бизнеса в Windows. Возможности ПО BToE.</span><span class="sxs-lookup"><span data-stu-id="f6880-p119">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app. BToE enables users to:</span></span>
  
- <span data-ttu-id="f6880-252">Вход пользователя в систему IP-телефона с помощью классического приложения Skype для бизнеса (с помощью ПК).</span><span class="sxs-lookup"><span data-stu-id="f6880-252">Sign in to their IP phone using their Skype for Business desktop app (using a PC)</span></span>
    
- <span data-ttu-id="f6880-253">Синхронизация функций блокировки телефона и ПК.</span><span class="sxs-lookup"><span data-stu-id="f6880-253">Synchronize Phone-Lock with PC lock</span></span>
    
- <span data-ttu-id="f6880-254">Звонок щелчком.</span><span class="sxs-lookup"><span data-stu-id="f6880-254">Click to call</span></span>
    
<span data-ttu-id="f6880-p120">ПО BToE можно настроить для работы в двух режимах:  *Auto*  (Авто) (по умолчанию) и *Manual*  (Ручной). Кроме того, эту функцию можно включить (по умолчанию) или отключить для пользователей с помощью штатных настроек Skype для бизнеса. При работе в режиме *Manual*  (Ручной) для сопряжения телефона с приложением Windows пользователям необходимо выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="f6880-p120">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  . It can also be enabled (default)/disabled for users using Skype for Business in-band settings. When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="f6880-258">**Развертывание ПО BToE для пользователей**</span><span class="sxs-lookup"><span data-stu-id="f6880-258">**To deploy BToE to users**</span></span>
  
1. <span data-ttu-id="f6880-259">Подключите телефон к порту ПК.</span><span class="sxs-lookup"><span data-stu-id="f6880-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![Снимок экрана, на котором показано подключение к компьютеру](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="f6880-p121">Скачайте и установите последнюю версию программного обеспечения по btoe на веб-сайте изготовителя из указанных ниже ссылок. Для более удобного взаимодействия с пользователем вы можете распространять и устанавливать программное обеспечение по btoe с помощью решения для распространения администратором, такого как Microsoft Endpoint Configuration Manager. Справку по настройке Configuration Manager можно найти [в разделе пакеты и программы в Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="f6880-p121">Download and install the latest BToE software from the manufacturer website from the links below. For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as Microsoft Endpoint Configuration Manager. For help using Configuration Manager, See [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>
    
   - [<span data-ttu-id="f6880-264">Сайт для скачивания ПО BToE для Polycom:</span><span class="sxs-lookup"><span data-stu-id="f6880-264">Polycom BToE Software Download site</span></span>](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [<span data-ttu-id="f6880-265">Скачать ПО BToE для Yealink</span><span class="sxs-lookup"><span data-stu-id="f6880-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
   - [<span data-ttu-id="f6880-266">Скачать ПО BToE для AudioCodes</span><span class="sxs-lookup"><span data-stu-id="f6880-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="f6880-p122">The server setting for BToE is set to **Enabled** and **Auto mode** by default. To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx).</span><span class="sxs-lookup"><span data-stu-id="f6880-p122">The server setting for BToE is set to **Enabled** and **Auto mode** by default. To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx).</span></span>
    
> [!NOTE]
> <span data-ttu-id="f6880-269">На данный момент ПО BToE не поддерживается на платформах Mac и VDI.</span><span class="sxs-lookup"><span data-stu-id="f6880-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="f6880-270">См. также:</span><span class="sxs-lookup"><span data-stu-id="f6880-270">Related topics</span></span>
[<span data-ttu-id="f6880-271">Получение номеров телефонов служб для Skype для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f6880-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[<span data-ttu-id="f6880-272">Возможности телефонной системы в Office 365</span><span class="sxs-lookup"><span data-stu-id="f6880-272">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="f6880-273">Страны и регионы, для которых доступны аудиоконференции и планы звонков</span><span class="sxs-lookup"><span data-stu-id="f6880-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
