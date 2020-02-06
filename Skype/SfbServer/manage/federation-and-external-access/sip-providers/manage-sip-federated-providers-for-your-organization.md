---
title: Управление федеративными поставщиками SIP в организации
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Сведения о настройке поддержки пользователей федеративных поставщиков SIP.
ms.openlocfilehash: 42845bfd39c65e60765ee8d3fd2f1e3a58a08aae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818370"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="98ad8-103">Управление поставщиками SIP-Федерации для Организации в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="98ad8-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="98ad8-104">Для настройки поддержки пользователей федеративных поставщиков SIP необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="98ad8-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="98ad8-105">Настройка одной или нескольких политик доступа внешних пользователей для поддержки взаимодействия с контактами в службах федерации SIP</span><span class="sxs-lookup"><span data-stu-id="98ad8-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="98ad8-106">Указание размещенных поставщиков, которые будут поддерживаться</span><span class="sxs-lookup"><span data-stu-id="98ad8-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="98ad8-107">Указание общедоступных служб обмена мгновенными сообщениями, которые вы хотите поддерживать</span><span class="sxs-lookup"><span data-stu-id="98ad8-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="98ad8-108">Создание и изменение общедоступных федеративных поставщиков SIP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="98ad8-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="98ad8-109">Общедоступная служба обмена мгновенными сообщениями позволяет пользователям в вашей организации обмениваться МГНОВЕНными сообщениями с пользователями служб обмена мгновенными сообщениями, предоставленных общедоступными поставщиками.</span><span class="sxs-lookup"><span data-stu-id="98ad8-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="98ad8-110">В Skype для бизнеса Server есть настройки общедоступного поставщика для обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="98ad8-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="98ad8-111">У каждого общедоступного поставщика задано полное доменное имя поставщика, а уровень проверки по умолчанию **позволяет пользователям общаться только с людьми из списка контактов, который использует этот поставщик**.</span><span class="sxs-lookup"><span data-stu-id="98ad8-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="98ad8-112">Как параметр по умолчанию, ни один из открытых поставщиков не включен.</span><span class="sxs-lookup"><span data-stu-id="98ad8-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="98ad8-113">Прежде чем включать общедоступные поставщики, необходимо завершить лицензионное соглашение и подготовиться к работе.</span><span class="sxs-lookup"><span data-stu-id="98ad8-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="98ad8-114">Вы можете включить поставщик, прежде чем приступить к работе с лицензией и обеспечением подготовки.</span><span class="sxs-lookup"><span data-stu-id="98ad8-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="98ad8-115">Пользователи не смогут общаться с контактами этих поставщиков, пока не завершится работа, необходимая предварительно.</span><span class="sxs-lookup"><span data-stu-id="98ad8-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="98ad8-116">Сведения о лицензировании и подготовке общедоступных поставщиков можно найти в разделе [Настройка политик для управления доступом пользователей](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="98ad8-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="98ad8-117">Для создания и изменения общедоступных поставщиков выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="98ad8-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="98ad8-118">Создание и изменение общедоступных поставщиков</span><span class="sxs-lookup"><span data-stu-id="98ad8-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="98ad8-119">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="98ad8-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="98ad8-120">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="98ad8-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="98ad8-121">На панели навигации слева выберите пункт **интеграция и внешний доступ**, а затем — **Федеративные поставщики SIP**.</span><span class="sxs-lookup"><span data-stu-id="98ad8-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="98ad8-122">Если вам нужно создать нового общедоступного поставщика, нажмите кнопку **создать** , а затем выберите пункт **общедоступный поставщик**.</span><span class="sxs-lookup"><span data-stu-id="98ad8-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="98ad8-123">Если вам нужно изменить запись из списка общедоступных поставщиков, выберите общедоступного поставщика, нажмите кнопку **изменить**, а затем выберите команду **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="98ad8-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="98ad8-124">На странице " **Изменение поставщика SIP-Федерации** " можно ввести или изменить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="98ad8-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="98ad8-125">**Включить связь с этим поставщиком**   . Если этот параметр включен, в обмен мгновенными сообщениями можно использовать пользователей этого поставщика.</span><span class="sxs-lookup"><span data-stu-id="98ad8-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="98ad8-126">**Имя поставщика:**   обязательное свойство введите имя поставщика, так как оно будет отображаться в списке поставщиков услуг-Федерации SIP.</span><span class="sxs-lookup"><span data-stu-id="98ad8-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="98ad8-127">**Служба пограничного доступа (FQDN):**   обязательное свойство введите полное доменное имя службы пограничного доступа для поставщика, который вы настраиваете.</span><span class="sxs-lookup"><span data-stu-id="98ad8-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="98ad8-128">Эти сведения предоставлены как элемент по умолчанию и должны изменяться только в том случае, если общедоступный поставщик вносит изменения в полное доменное имя службы Edge Access на общедоступном поставщике.</span><span class="sxs-lookup"><span data-stu-id="98ad8-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="98ad8-129">**Уровень проверки по умолчанию:**   Настройка по умолчанию, **разрешающая пользователям общаться с людьми из списка контактов, которые используют этот поставщик** , ограничивает общение с контактами, которые вы приняли, и находятся в вашем списке контактов.</span><span class="sxs-lookup"><span data-stu-id="98ad8-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="98ad8-130">Выбрав **параметр Разрешить пользователям общаться с кем угодно с помощью этого поставщика** , вы удаляете ограничение, которое вы должны получить и принять приглашение на контакт.</span><span class="sxs-lookup"><span data-stu-id="98ad8-130">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="98ad8-131">Этот параметр не ограничивает круг пользователей, которые могут общаться с вами в сети общедоступного поставщика.</span><span class="sxs-lookup"><span data-stu-id="98ad8-131">This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="98ad8-132">Завершив настройку параметров **, нажмите кнопку Сохранить для** сохранения или кнопку **Отмена** , чтобы отменить изменения.</span><span class="sxs-lookup"><span data-stu-id="98ad8-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="98ad8-133">Создание и изменение размещенных служб федерации SIP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="98ad8-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="98ad8-134">Подключение к службе обмена мгновенными сообщениями (IM) позволяет пользователям в вашей организации общаться с пользователями служб обмена мгновенными сообщениями, предоставленными поставщиками услуг хостинга.</span><span class="sxs-lookup"><span data-stu-id="98ad8-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="98ad8-135">Для каждого поставщика услуг размещения задано полное доменное имя поставщика, а уровень проверки по умолчанию **позволяет пользователям общаться только с людьми из списка контактов, который использует этот поставщик**.</span><span class="sxs-lookup"><span data-stu-id="98ad8-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="98ad8-136">Для создания и изменения размещенных поставщиков выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="98ad8-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="98ad8-137">Создание и изменение размещенных поставщиков</span><span class="sxs-lookup"><span data-stu-id="98ad8-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="98ad8-138">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="98ad8-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="98ad8-139">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="98ad8-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="98ad8-140">На панели навигации слева выберите пункт **интеграция и внешний доступ**, а затем — **Федеративные поставщики SIP**.</span><span class="sxs-lookup"><span data-stu-id="98ad8-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="98ad8-141">Если вам нужно создать нового поставщика услуг размещения, нажмите кнопку **создать** , а затем выберите пункт **внутрипроцессный поставщик**.</span><span class="sxs-lookup"><span data-stu-id="98ad8-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="98ad8-142">Если вам нужно изменить запись из списка размещенных поставщиков, выберите поставщика услуг, нажмите кнопку **изменить**, а затем выберите пункт **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="98ad8-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="98ad8-143">На странице " **Изменение поставщика SIP-Федерации** " можно ввести или изменить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="98ad8-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="98ad8-144">**Включите связь с этим поставщиком**   , выбрав этот параметр, чтобы включить связь с пользователями этого поставщика.</span><span class="sxs-lookup"><span data-stu-id="98ad8-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="98ad8-145">**Имя поставщика:**   обязательное свойство введите имя поставщика, так как оно будет отображаться в списке поставщиков услуг-Федерации SIP.</span><span class="sxs-lookup"><span data-stu-id="98ad8-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="98ad8-146">**Служба пограничного доступа (полное доменное имя):**   обязательное свойство введите полное доменное имя службы Edge для доступного поставщика услуг размещения, который вы настраиваете.</span><span class="sxs-lookup"><span data-stu-id="98ad8-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="98ad8-147">Эти данные должны предоставляться поставщиком услуг размещения и должны изменяться только в том случае, если поставщик услуг хостинга вносит изменения в полное доменное имя службы EDGE на доступ на размещенном поставщике.</span><span class="sxs-lookup"><span data-stu-id="98ad8-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="98ad8-148">**Уровень проверки по умолчанию:**   Настройка по умолчанию, **разрешающая пользователям общаться с людьми из списка контактов, которые используют этот поставщик** , ограничивает общение с контактами, которые вы приняли, и находятся в вашем списке контактов.</span><span class="sxs-lookup"><span data-stu-id="98ad8-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="98ad8-149">Выбрав **параметр Разрешить пользователям общаться с кем угодно с помощью этого поставщика** , вы удаляете ограничение, которое вы должны получить и принять приглашение на контакт.</span><span class="sxs-lookup"><span data-stu-id="98ad8-149">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="98ad8-150">Этот параметр не ограничивает список пользователей, которые могут общаться с вами из сети размещенного поставщика.</span><span class="sxs-lookup"><span data-stu-id="98ad8-150">This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="98ad8-151">Завершив настройку параметров **, нажмите кнопку Сохранить для** сохранения или кнопку **Отмена** , чтобы отменить изменения.</span><span class="sxs-lookup"><span data-stu-id="98ad8-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="98ad8-152">См. также</span><span class="sxs-lookup"><span data-stu-id="98ad8-152">See Also</span></span>


[<span data-ttu-id="98ad8-153">Настройка политик для контроля использования открытых пользователей</span><span class="sxs-lookup"><span data-stu-id="98ad8-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="98ad8-154">Включение или отключение федерации и подключение для общедоступного обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="98ad8-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

