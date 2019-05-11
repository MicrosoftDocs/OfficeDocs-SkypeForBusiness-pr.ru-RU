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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Узнайте, как для настройки поддержки пользователей SIP федеративных поставщиков.
ms.openlocfilehash: 64b5dcd657b72f03b25fe6de2ff6c0cda21b676d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33903181"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="f0129-103">Управление поставщиками SIP федеративных для вашей организации в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="f0129-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="f0129-104">Для настройки поддержки пользователей SIP федеративных поставщиков, необходимо выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="f0129-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="f0129-105">Настройте один или несколько политик доступа внешних пользователей для поддержки взаимодействия с контактами SIP федеративного поставщика</span><span class="sxs-lookup"><span data-stu-id="f0129-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="f0129-106">Указать размещенных поставщиков, которых необходимо обеспечить поддержку</span><span class="sxs-lookup"><span data-stu-id="f0129-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="f0129-107">Указать, какие общедоступных поставщиков обмена мгновенными Сообщениями, необходимо обеспечить поддержку</span><span class="sxs-lookup"><span data-stu-id="f0129-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="f0129-108">Создание или изменение общедоступных поставщиков SIP федеративных в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="f0129-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="f0129-109">Обмен Мгновенными сообщениями подключение к общедоступным системам позволяет пользователям организации использовать мгновенные сообщения для взаимодействия с пользователями служб мгновенных сообщений, предоставляемых общедоступных поставщиков.</span><span class="sxs-lookup"><span data-stu-id="f0129-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="f0129-110">Скайп для Business Server имеет общедоступный поставщик конфигурации для обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="f0129-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="f0129-111">Каждый поставщик общих настроить поставщика пограничного полное доменное имя сервера и уровень проверки по умолчанию **Разрешить пользователям связываться только с людей в свой список контактов, использующие этот поставщик**.</span><span class="sxs-lookup"><span data-stu-id="f0129-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="f0129-112">Как значения по умолчанию ни один из общедоступных поставщиков включены.</span><span class="sxs-lookup"><span data-stu-id="f0129-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="f0129-113">Следует выполнить лицензионное соглашение и действиях перед включением общедоступных поставщиков по подготовке.</span><span class="sxs-lookup"><span data-stu-id="f0129-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="f0129-114">Можно включить поставщик перед завершением лицензирования и действиях по подготовке.</span><span class="sxs-lookup"><span data-stu-id="f0129-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="f0129-115">Пользователи не смогут общаться с контактами в тех поставщиков вплоть до завершения работы необходимые предварительные.</span><span class="sxs-lookup"><span data-stu-id="f0129-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="f0129-116">[Настройка политик для контроля доступа пользователей общедоступных служб](../external-access-policies/configure-policies-to-control-public-user-access.md)сведения о лицензировании и подготовки общедоступных поставщиков см.</span><span class="sxs-lookup"><span data-stu-id="f0129-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="f0129-117">Используйте следующую процедуру для создания или изменения общедоступных поставщиков.</span><span class="sxs-lookup"><span data-stu-id="f0129-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="f0129-118">Чтобы создать или изменить общедоступных поставщиков</span><span class="sxs-lookup"><span data-stu-id="f0129-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="f0129-119">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f0129-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f0129-120">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="f0129-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f0129-121">В левой панели навигации щелкните **Федерация и внешний доступ**и нажмите кнопку **Федеративных поставщиков SIP**.</span><span class="sxs-lookup"><span data-stu-id="f0129-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="f0129-122">Если вам необходимо создать нового общедоступного поставщика, нажмите кнопку **Создать** и выберите **общедоступного поставщика**.</span><span class="sxs-lookup"><span data-stu-id="f0129-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="f0129-123">Если необходимо изменить запись в списке общедоступных поставщиков, выберите общедоступного поставщика, нажмите кнопку **Изменить**, а затем щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="f0129-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="f0129-124">На странице **Изменить федеративного поставщика SIP** можно ввести или изменить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f0129-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="f0129-125">**Разрешить взаимодействие с этим поставщиком**   Выбор этого параметра включает обмен мгновенными Сообщениями с пользователями данного поставщика.</span><span class="sxs-lookup"><span data-stu-id="f0129-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="f0129-126">**Имя поставщика:**   обязательное свойство, введите имя поставщика, каким оно будет отображаться в списке федеративных поставщиков SIP.</span><span class="sxs-lookup"><span data-stu-id="f0129-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="f0129-127">**Доступ к служба пограничного сервера (FQDN):**   обязательное свойство, введите полное доменное имя пограничного сервера доступа службы поставщика, для которого выполняется настройка.</span><span class="sxs-lookup"><span data-stu-id="f0129-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="f0129-128">Эти сведения предоставляются как элемент по умолчанию и следует изменять только если общедоступный поставщик вносит изменения на полное доменное имя пограничного сервера доступа службы поставщика общих.</span><span class="sxs-lookup"><span data-stu-id="f0129-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="f0129-129">**По умолчанию уровень проверки:**   значение по умолчанию, **Разрешить пользователям связываться с людей в свой список контактов, использующие этот поставщик** ограничит связи контактам, которые были выбраны и находятся в список контактов.</span><span class="sxs-lookup"><span data-stu-id="f0129-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="f0129-130">Выбор **Разрешить пользователям связываться с всем пользователям с помощью данного поставщика** Удаляет ограничение, что необходимо получено и принятия контакта пригласить.</span><span class="sxs-lookup"><span data-stu-id="f0129-130">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="f0129-131">Этот параметр ограничивает пользователей, которые смогут связаться с общедоступным поставщиком сети.</span><span class="sxs-lookup"><span data-stu-id="f0129-131">This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="f0129-132">Если все настройку параметров, нажмите кнопку **зафиксировать** , чтобы сохранить или нажмите кнопку **Отмена** , чтобы отменить изменения.</span><span class="sxs-lookup"><span data-stu-id="f0129-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="f0129-133">Создание или изменение размещенной SIP федеративных поставщиков в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="f0129-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="f0129-134">Размещенные поставщиком услуг обмена Мгновенными сообщениями подключения к позволяет пользователям организации использовать мгновенные сообщения для взаимодействия с пользователями служб обмена мгновенными Сообщениями, предоставляемых размещенными поставщиками и системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="f0129-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="f0129-135">Каждый размещенного в узле поставщика следует настроить поставщика пограничного полное доменное имя сервера и уровень проверки по умолчанию **Разрешить пользователям связываться только с людей в свой список контактов, использующие этот поставщик**.</span><span class="sxs-lookup"><span data-stu-id="f0129-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="f0129-136">Используйте следующую процедуру, чтобы создать или изменить размещенных поставщиков.</span><span class="sxs-lookup"><span data-stu-id="f0129-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="f0129-137">Чтобы создать или изменить размещенных поставщиков</span><span class="sxs-lookup"><span data-stu-id="f0129-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="f0129-138">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f0129-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f0129-139">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="f0129-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f0129-140">В левой панели навигации щелкните **Федерация и внешний доступ**и нажмите кнопку **Федеративных поставщиков SIP**.</span><span class="sxs-lookup"><span data-stu-id="f0129-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="f0129-141">Если вам необходимо создать новый поставщик размещенных в узлах, нажмите кнопку **Создать** и выберите **размещенного в узле поставщика**.</span><span class="sxs-lookup"><span data-stu-id="f0129-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="f0129-142">Если необходимо изменить запись из списка размещенных в узлах поставщиков, выберите размещенного в узле поставщика, нажмите кнопку **Изменить**, а затем щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="f0129-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="f0129-143">На странице **Изменить федеративного поставщика SIP** можно ввести или изменить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f0129-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="f0129-144">**Разрешить взаимодействие с этим поставщиком**   Выбор этого параметра разрешается связь с пользователями данного поставщика.</span><span class="sxs-lookup"><span data-stu-id="f0129-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="f0129-145">**Имя поставщика:**   обязательное свойство, введите имя поставщика, каким оно будет отображаться в списке федеративных поставщиков SIP.</span><span class="sxs-lookup"><span data-stu-id="f0129-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="f0129-146">**Доступ к служба пограничного сервера (FQDN):**   обязательное свойство, введите полное доменное имя пограничного сервера доступа службы размещенной поставщика, настройка которых осуществляется.</span><span class="sxs-lookup"><span data-stu-id="f0129-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="f0129-147">Эти сведения предоставляются размещенного в узле поставщика и следует изменять только если размещенного в узле поставщика вносит изменения на полное доменное имя пограничного сервера доступа службы у поставщика в размещенной.</span><span class="sxs-lookup"><span data-stu-id="f0129-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="f0129-148">**По умолчанию уровень проверки:**   значение по умолчанию, **Разрешить пользователям связываться с людей в свой список контактов, использующие этот поставщик** ограничит связи контактам, которые были выбраны и находятся в список контактов.</span><span class="sxs-lookup"><span data-stu-id="f0129-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="f0129-149">Выбор **Разрешить пользователям связываться с всем пользователям с помощью данного поставщика** Удаляет ограничение, что необходимо получено и принятия контакта пригласить.</span><span class="sxs-lookup"><span data-stu-id="f0129-149">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="f0129-150">Этот параметр ограничивает пользователей, которые можно связаться с вами из сети размещенной поставщика.</span><span class="sxs-lookup"><span data-stu-id="f0129-150">This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="f0129-151">Если все настройку параметров, нажмите кнопку **зафиксировать** , чтобы сохранить или нажмите кнопку **Отмена** , чтобы отменить изменения.</span><span class="sxs-lookup"><span data-stu-id="f0129-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="f0129-152">См. также</span><span class="sxs-lookup"><span data-stu-id="f0129-152">See Also</span></span>


[<span data-ttu-id="f0129-153">Настройка политик для контроля доступа пользователей общедоступных служб</span><span class="sxs-lookup"><span data-stu-id="f0129-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="f0129-154">Включение или отключение федерации и подключение для общедоступного обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="f0129-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

