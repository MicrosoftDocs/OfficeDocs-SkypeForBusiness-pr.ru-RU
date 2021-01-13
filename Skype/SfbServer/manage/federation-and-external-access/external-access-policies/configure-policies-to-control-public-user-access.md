---
title: Настройка политик для управления общим доступом пользователей
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
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
description: Ublic instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM services.
ms.openlocfilehash: 28bb1c94cb42068fe99f07a6608a3ac1c50991ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823595"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a><span data-ttu-id="518d3-103">Настройка политик для управления доступом общедоступных пользователей в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="518d3-103">Configure policies to control public user access in Skype for Business Server</span></span>

<span data-ttu-id="518d3-104">Подключение к общедоступным службам обмена мгновенными сообщениями позволяет пользователям в организации использовать обмен мгновенными сообщениями для связи с пользователями служб обмена мгновенными сообщениями, предоставляемых общедоступными поставщиками услуг обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="518d3-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers.</span></span> <span data-ttu-id="518d3-105">Настраивается одна или несколько политик доступа внешних пользователей для управления возможностью совместной работы общедоступных пользователей с внутренними пользователями Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="518d3-105">You configure one or more external user access policies to control whether public users can collaborate with internal Skype for Business Server users.</span></span> <span data-ttu-id="518d3-106">Подключение к общедоступным службам обмена мгновенными сообщениями — это добавленная функция, которая зависит от конфигурации развертывания и пользователей.</span><span class="sxs-lookup"><span data-stu-id="518d3-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="518d3-107">Это также зависит от предоставления службы у поставщика общедоступных служб мгновенных услуг.</span><span class="sxs-lookup"><span data-stu-id="518d3-107">It also depends on the provisioning of the service at the public IM provider.</span></span> 

<span data-ttu-id="518d3-108">Для управления доступом пользователей общедоступных служб можно настроить политики на глобальном уровне, уровне сайта и пользовательском уровне.</span><span class="sxs-lookup"><span data-stu-id="518d3-108">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="518d3-109">Параметры политики Skype для бизнеса Server, применяемые на одном уровне политики, могут переопределять параметры, применяемые на другом уровне политики.</span><span class="sxs-lookup"><span data-stu-id="518d3-109">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="518d3-110">Приоритет политик в Skype для бизнеса Server: политика пользователя (наибольшее влияние) переопределяет политику сайта, а политика сайта переопределяет глобальную политику (наименьшее влияние). </span><span class="sxs-lookup"><span data-stu-id="518d3-110">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="518d3-111">То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.</span><span class="sxs-lookup"><span data-stu-id="518d3-111">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="518d3-p103">В случае приглашений к обмену мгновенными сообщениями ответ зависит от клиентского ПО. Запрос принимается, если внешние отправители не блокированы пользовательским правилом (то есть настройками пользовательских списков клиентов **Разрешить** и **Заблокировать** для клиентов). Кроме того, приглашения к обмену мгновенными сообщениями могут быть блокированы, если пользователь выбирает блокировку всех мгновенных сообщений от пользователей, не входящих в его список **Разрешить**.</span><span class="sxs-lookup"><span data-stu-id="518d3-p103">In the case of IM invitations, the response depends on the client software. The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists). Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>



> [!NOTE]  
> <span data-ttu-id="518d3-115">Политики управления доступом пользователей общедоступных служб можно настроить даже при отсутствии федерации в организации.</span><span class="sxs-lookup"><span data-stu-id="518d3-115">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="518d3-116">Но настроенные политики действуют только при включенных федеративных отношениях для организации.</span><span class="sxs-lookup"><span data-stu-id="518d3-116">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="518d3-117">Подробные сведения о включаемой федерации см. в сведениях о [включаемом или отключаемом удаленном доступе пользователей.](../access-edge/enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="518d3-117">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span> <span data-ttu-id="518d3-118">Кроме того, если вы указываете политику пользователей для управления доступом пользователей к общедоступным системам, эта политика применяется только к пользователям, которые включены в Skype для бизнеса Server и настроены на использование этой политики.</span><span class="sxs-lookup"><span data-stu-id="518d3-118">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span> <span data-ttu-id="518d3-119">Дополнительные сведения об указании общедоступных пользователей, которые могут войти в Skype для бизнеса Server, см. в документе "Назначение политики доступа [внешних пользователей".](assign-an-external-user-access-policy.md)</span><span class="sxs-lookup"><span data-stu-id="518d3-119">For details about specifying public users that can sign in to Skype for Business Server, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>


<span data-ttu-id="518d3-120">Для настройки политики, поддерживающей доступ пользователей одного или нескольких общедоступных поставщиков услуг обмена мгновенными сообщениями, используется следующая процедура.</span><span class="sxs-lookup"><span data-stu-id="518d3-120">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="518d3-121">Настройка политики внешнего доступа для поддержки доступа пользователей общедоступных служб</span><span class="sxs-lookup"><span data-stu-id="518d3-121">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="518d3-122">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="518d3-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="518d3-123">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="518d3-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="518d3-124">На левой панели навигации щелкните **Внешний доступ пользователей**, затем щелкните **Политика внешнего доступа**.</span><span class="sxs-lookup"><span data-stu-id="518d3-124">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="518d3-125">На странице **Политика внешнего доступа** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="518d3-125">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="518d3-126">Чтобы настроить глобальную политику для поддержки доступа пользователей общедоступных служб, щелкните глобальную политику, щелкните **Изменить**, а затем щелкните **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="518d3-126">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="518d3-p105">Чтобы создать новую политику сайта, щелкните **Создать**, затем щелкните **Политика сайта**. В разделе **Выбор сайта** щелкните подходящий сайт в списке и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="518d3-p105">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="518d3-p106">Чтобы создать новую политику для пользователей, щелкните **Создать**, затем щелкните **Политика пользователей**. В окне **Создание политики внешнего доступа** задайте в поле **Имя** уникальное имя, показывающее область применения этой политики (например, **EnablePublicUsers** для пользовательской политики, разрешающей взаимодействие с пользователями общедоступных служб).</span><span class="sxs-lookup"><span data-stu-id="518d3-p106">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="518d3-131">Чтобы изменить существующую политику, щелкните ее в таблице, щелкните **Изменить**, затем **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="518d3-131">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="518d3-132">(Необязательно) Если необходимо добавить или изменить описание, укажите сведения для этой политики в пункте **Описание**.</span><span class="sxs-lookup"><span data-stu-id="518d3-132">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="518d3-133">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="518d3-133">Do one of the following:</span></span>
    
      - <span data-ttu-id="518d3-134">Чтобы разрешить для политики доступ пользователей общедоступных служб, установите флажок **Разрешить взаимодействие с незарегистрированными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="518d3-134">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="518d3-135">Чтобы запретить для политики доступ пользователей общедоступных служб, снимите флажок **Разрешить взаимодействие с незарегистрированными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="518d3-135">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="518d3-136">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="518d3-136">Click **Commit**.</span></span>

<span data-ttu-id="518d3-137">Чтобы включить доступ пользователей общедоступных служб, необходимо также включить в организации поддержку федерации.</span><span class="sxs-lookup"><span data-stu-id="518d3-137">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="518d3-138">For details, see [Configure policies to control federated user access in Skype for Business Server.](configure-policies-to-control-federated-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="518d3-138">For details, see [Configure policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="518d3-139">В случае пользовательской политики, также необходимо настроить и применить политику к пользователям общедоступных служб, которым требуется разрешить совместную работу с пользователями общедоступных служб.</span><span class="sxs-lookup"><span data-stu-id="518d3-139">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> 


## <a name="see-also"></a><span data-ttu-id="518d3-140">См. также</span><span class="sxs-lookup"><span data-stu-id="518d3-140">See Also</span></span>

[<span data-ttu-id="518d3-141">Управление федеративными поставщиками SIP в организации</span><span class="sxs-lookup"><span data-stu-id="518d3-141">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
