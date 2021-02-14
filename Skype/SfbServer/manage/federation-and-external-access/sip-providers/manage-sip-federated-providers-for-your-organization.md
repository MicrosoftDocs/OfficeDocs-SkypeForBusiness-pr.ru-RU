---
title: Управление федеративными поставщиками SIP в организации
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Узнайте, как настроить поддержку для пользователей федераированных поставщиков SIP.
ms.openlocfilehash: 8d4c6224a66454f8fb28bb4f991faf6ad672f596
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823569"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="48d55-103">Управление федератными поставщиками SIP для организации в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="48d55-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="48d55-104">Для настройки поддержки пользователей федеративных поставщиков SIP необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="48d55-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="48d55-105">Настроить одну или несколько политик доступа внешних пользователей для поддержки взаимодействия с контактами федеративного поставщика SIP.</span><span class="sxs-lookup"><span data-stu-id="48d55-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="48d55-106">Указать размещенных поставщиков, которых планируется поддерживать.</span><span class="sxs-lookup"><span data-stu-id="48d55-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="48d55-107">Указать поставщиков общедоступного обмена мгновенными сообщениями, которых планируется поддерживать.</span><span class="sxs-lookup"><span data-stu-id="48d55-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="48d55-108">Создание или изменение общедоступных федераированных поставщиков SIP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="48d55-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="48d55-109">Подключение к общедоступным службам обмена мгновенными сообщениями позволяет пользователям в организации использовать обмен мгновенными сообщениями для связи с пользователями служб обмена мгновенными сообщениями, предоставляемых общедоступными поставщиками услуг обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="48d55-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="48d55-110">В Skype для бизнеса Server есть конфигурации общедоступных поставщиков для обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="48d55-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="48d55-111">Каждый общедоступный поставщик настраивается с использованием полного доменного имени его сервера, а уровень проверки по умолчанию позволяет пользователям общаться только с пользователями из списка контактов, которые используют этого **поставщика.**</span><span class="sxs-lookup"><span data-stu-id="48d55-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="48d55-112">По умолчанию ни один из общедоступных поставщиков не включен.</span><span class="sxs-lookup"><span data-stu-id="48d55-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="48d55-113">Перед включением общедоступных поставщиков необходимо выполнить условия лицензионного соглашения и работы по его предоставлению.</span><span class="sxs-lookup"><span data-stu-id="48d55-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="48d55-114">Вы можете включить поставщика перед завершением работы по лицензированию и предоставлению.</span><span class="sxs-lookup"><span data-stu-id="48d55-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="48d55-115">Пользователи не смогут взаимодействовать с контактами этих поставщиков, пока не будет выполнена необходимая работа.</span><span class="sxs-lookup"><span data-stu-id="48d55-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="48d55-116">Подробные сведения о лицензировании и предоставлении общедоступных поставщиков см. в подстроке "Настройка политик для управления доступом [общедоступных пользователей".](../external-access-policies/configure-policies-to-control-public-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="48d55-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="48d55-117">Используйте следующую процедуру для создания или изменения общедоступных поставщиков.</span><span class="sxs-lookup"><span data-stu-id="48d55-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="48d55-118">Чтобы создать или изменить общедоступного поставщика</span><span class="sxs-lookup"><span data-stu-id="48d55-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="48d55-119">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="48d55-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="48d55-120">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="48d55-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="48d55-121">На левой панели навигации щелкните **Федерация и внешний доступ**, затем щелкните **Федеративные поставщики SIP**.</span><span class="sxs-lookup"><span data-stu-id="48d55-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="48d55-122">Если необходимо создать нового общедоступного поставщика, щелкните **Создать**, затем **Общедоступный поставщик**.</span><span class="sxs-lookup"><span data-stu-id="48d55-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="48d55-123">Если необходимо изменить запись в списке общедоступных поставщиков, выберите общедоступного поставщика, щелкните **Изменить**, затем **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="48d55-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="48d55-124">На странице **Изменить федеративного поставщика SIP** можно указать или изменить следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="48d55-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="48d55-125">**Разрешить взаимодействие с этим поставщиком**   Выбор этого параметра включает обмен мгновенными сообщениями с пользователями данного поставщика.</span><span class="sxs-lookup"><span data-stu-id="48d55-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="48d55-126">**Имя поставщика:**    обязательное свойство, введите имя поставщика, каким оно будет отображаться в списке федеративных поставщиков SIP.</span><span class="sxs-lookup"><span data-stu-id="48d55-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="48d55-127">**Служба доступа (FQDN):**   Обязательное свойство, введите полное доменное имя службы по краям доступа настраиваемого поставщика.</span><span class="sxs-lookup"><span data-stu-id="48d55-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="48d55-128">Эти сведения предоставляются в качестве элемента по умолчанию и должны изменяться только в том случае, если общедоступный поставщик внося изменения в FQDN службы по границе доступа у поставщика.</span><span class="sxs-lookup"><span data-stu-id="48d55-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="48d55-129">**Уровень проверки по умолчанию:**    параметр по умолчанию **Разрешить пользователям взаимодействовать с людьми в своих списках контактов, которые используют этого поставщика** ограничивает связь с контактами, принятые данным пользователем и включенным им в свой список контактов.</span><span class="sxs-lookup"><span data-stu-id="48d55-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="48d55-p104">Выбор параметра **Разрешить пользователям взаимодействовать со всеми, кто работает с тем же поставщиком** снимает ограничения на общение с контактами того или иного поставщика. Любой пользователь из сети общедоступного поставщика может связываться с пользователями данной организации.</span><span class="sxs-lookup"><span data-stu-id="48d55-p104">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="48d55-132">Завершив настройку параметров, нажмите кнопку **Сохранить**, чтобы сохранить параметры, или **Отмена**, чтобы отменить изменения.</span><span class="sxs-lookup"><span data-stu-id="48d55-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="48d55-133">Создание или изменение серверных федераированных поставщиков SIP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="48d55-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="48d55-134">Возможность подключения к службам обмена мгновенными сообщениями поставщика услуг интернета позволяет пользователям в организации использовать мгновенные сообщения для связи с пользователями служб обмена мгновенными сообщениями, предоставляемых поставщиками услуг обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="48d55-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="48d55-135">Каждый размещенный в узле поставщик настраивается с полным доменным именем пограничного сервера поставщика услуг и уровнем проверки по умолчанию **Разрешить пользователям взаимодействовать только с людьми в своих списках контактов, которые пользуются услугами данного поставщика**.</span><span class="sxs-lookup"><span data-stu-id="48d55-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="48d55-136">Используйте следующую процедуру для создания или изменения поставщиков.</span><span class="sxs-lookup"><span data-stu-id="48d55-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="48d55-137">Чтобы создать или изменить размещенных в узлах поставщиков</span><span class="sxs-lookup"><span data-stu-id="48d55-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="48d55-138">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="48d55-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="48d55-139">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="48d55-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="48d55-140">На левой панели навигации щелкните **Федерация и внешний доступ**, затем щелкните **Федеративные поставщики SIP**.</span><span class="sxs-lookup"><span data-stu-id="48d55-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="48d55-141">Если требуется создать нового размещенного в узле поставщика, щелкните **Создать**, а затем щелкните **Размещенный в узле поставщик**.</span><span class="sxs-lookup"><span data-stu-id="48d55-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="48d55-142">Если требуется изменить запись из списка размещенных в узлах поставщиков, выберите размещенного в узле поставщика, щелкните **Изменить**, затем щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="48d55-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="48d55-143">На странице **Изменить федеративного поставщика SIP** можно указать или изменить следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="48d55-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="48d55-144">**Включить связь с данным поставщиком**   При выборе этого параметра разрешается связь с пользователями данного поставщика.</span><span class="sxs-lookup"><span data-stu-id="48d55-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="48d55-145">**Имя поставщика:**    обязательное свойство, введите имя поставщика, каким оно будет отображаться в списке федеративных поставщиков SIP.</span><span class="sxs-lookup"><span data-stu-id="48d55-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="48d55-146">**Служба доступа (FQDN):**   Обязательное свойство, введите полное доменное имя службы по краям доступа настраиваемого поставщика.</span><span class="sxs-lookup"><span data-stu-id="48d55-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="48d55-147">Эти сведения должны предоставляться размещенным в узле поставщиком и их допускается изменять только в том случае, если размещенный в узле поставщик изменяет полное доменное имя службы пограничного доступа на размещенном в узле поставщике.</span><span class="sxs-lookup"><span data-stu-id="48d55-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="48d55-148">**Уровень проверки по умолчанию:**    параметр по умолчанию **Разрешить пользователям взаимодействовать с людьми в своих списках контактов, которые используют этого поставщика** ограничивает связь с контактами, принятые данным пользователем и включенным им в свой список контактов.</span><span class="sxs-lookup"><span data-stu-id="48d55-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="48d55-p106">При выборе параметра **Разрешить связь со всеми, кто пользуется услугами данного поставщика** снимается ограничение, содержащее требование получения и принятия приглашения установить контакт. Этим параметром не ограничивается круг пользователей, которые могут связываться с вами из сети размещенного в узле поставщика.</span><span class="sxs-lookup"><span data-stu-id="48d55-p106">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="48d55-151">Завершив настройку параметров, нажмите кнопку **Зафиксировать**, чтобы сохранить параметры, или **Отмена**, чтобы отменить изменения.</span><span class="sxs-lookup"><span data-stu-id="48d55-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="48d55-152">См. также</span><span class="sxs-lookup"><span data-stu-id="48d55-152">See Also</span></span>


[<span data-ttu-id="48d55-153">Настройка политик для управления доступом общедоступных пользователей</span><span class="sxs-lookup"><span data-stu-id="48d55-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="48d55-154">Включение или отключение федерации и подключение для общедоступного обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="48d55-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

