---
title: 'Lync Server 2013: Настройка политик для управления доступом открытых пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a967f186d924a199b007ceba8390bf968253ec72
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520416"
---
# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a><span data-ttu-id="cc648-102">Настройка политик для управления доступом открытых пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc648-102">Configure policies to control public user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc648-103">_**Последнее изменение темы:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="cc648-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="cc648-104">Подключение к общедоступным службам обмена мгновенными сообщениями позволяет пользователям в Организации использовать обмен мгновенными сообщениями для общения с пользователями служб обмена мгновенными сообщениями, предоставляемыми поставщиками общедоступных служб обмена мгновенными сообщениями, в том числе сетью Windows Live, Yahoo \! и AOL.</span><span class="sxs-lookup"><span data-stu-id="cc648-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live network of Internet services, Yahoo\!, and AOL.</span></span> <span data-ttu-id="cc648-105">Вы настраиваете одну или несколько политик доступа внешних пользователей, чтобы определять, могут ли общедоступные пользователи совместно работать с внутренними пользователями Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cc648-105">You configure one or more external user access policies to control whether public users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="cc648-106">Общедоступная служба обмена мгновенными сообщениями — это дополнительный компонент, который использует конфигурацию развертывания и пользователей.</span><span class="sxs-lookup"><span data-stu-id="cc648-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="cc648-107">Он также зависит от подготовки службы к общедоступному поставщику услуг обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="cc648-107">It also depends on the provisioning of the service at the public IM provider.</span></span> <span data-ttu-id="cc648-108">Сведения о том, как подготовить развертывание к использованию общедоступных поставщиков, можно найти в руководстве по подготовке общедоступной службы обмена мгновенными сообщениями для Microsoft Lync Server, Office Communications Server и сервера Live Communications Server. [https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)</span><span class="sxs-lookup"><span data-stu-id="cc648-108">For information on how to provision your deployment to use the public providers, see the “Public IM Connectivity Provisioning Guide for Microsoft Lync Server, Office Communications Server, and Live Communications Server” guide: [https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="cc648-109">С 1 сентября 2012 г. лицензия подписки на общедоступные службы обмена мгновенными сообщениями Microsoft Lync ("PIC усл") больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="cc648-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="cc648-110">Клиенты с активными лицензиями смогут продолжать Федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="cc648-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="cc648-111">Messenger до даты завершения работы службы.</span><span class="sxs-lookup"><span data-stu-id="cc648-111">Messenger until the service shut down date.</span></span> <span data-ttu-id="cc648-112">Дата окончания срока жизни 2014 для AOL и Yahoo!</span><span class="sxs-lookup"><span data-stu-id="cc648-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="cc648-113">объявлено.</span><span class="sxs-lookup"><span data-stu-id="cc648-113">has been announced.</span></span> <span data-ttu-id="cc648-114">Дополнительные сведения см <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cc648-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="cc648-115">УСЛ PIC является лицензией на месяц на уровне пользователя, которая требуется для Lync Server или Office Communications Server для Федерации с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="cc648-115">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="cc648-116">Messenger.</span><span class="sxs-lookup"><span data-stu-id="cc648-116">Messenger.</span></span> <span data-ttu-id="cc648-117">Способность корпорации Майкрософт предоставлять эту службу зависит от поддержки компании Yahoo!, основного соглашения, для которого выполняется обмотка.</span><span class="sxs-lookup"><span data-stu-id="cc648-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="cc648-118">Lync — это мощное средство для связи между организациями и пользователями мира.</span><span class="sxs-lookup"><span data-stu-id="cc648-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="cc648-119">Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандарту Lync CAL.</span><span class="sxs-lookup"><span data-stu-id="cc648-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="cc648-120">В этот список будет добавлена Федерация Skype, что позволит пользователям Lync достичь сотен миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="cc648-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="cc648-121">Чтобы получить доступ к сайту подготовки общедоступной службы обмена мгновенными сообщениями Microsoft Lync Server, используйте следующую ссылку: [https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)</span><span class="sxs-lookup"><span data-stu-id="cc648-121">To access the Microsoft Lync Server Public IM Connectivity Provisioning site, use the following link: [https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)</span></span>

<span data-ttu-id="cc648-122">Для управления доступом пользователей общедоступных служб можно настроить политики на глобальном уровне, уровне сайта и пользовательском уровне.</span><span class="sxs-lookup"><span data-stu-id="cc648-122">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="cc648-123">Дополнительные сведения о типах политик, которые можно настроить, приведены в статье [Настройка поддержки доступа внешних пользователей в Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) в документации по развертыванию или в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="cc648-123">For details about the types of policies that you can configure, see [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) in the Deployment documentation or the Planning documentation.</span></span> <span data-ttu-id="cc648-124">Параметры политики Lync Server, применяемые на одном уровне политики, могут переопределять параметры, применяемые на другом уровне политики.</span><span class="sxs-lookup"><span data-stu-id="cc648-124">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="cc648-125">Приоритет политики Lync Server: политика пользователя (наиболее влияние) переопределяет политику сайта, а затем политика сайта переопределяет глобальную политику (наименее влияние).</span><span class="sxs-lookup"><span data-stu-id="cc648-125">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="cc648-126">То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.</span><span class="sxs-lookup"><span data-stu-id="cc648-126">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="cc648-p106">В случае приглашений к обмену мгновенными сообщениями ответ зависит от клиентского ПО. Запрос принимается, если внешние отправители не блокированы пользовательским правилом (то есть настройками пользовательских списков клиентов **Разрешить** и **Заблокировать** для клиентов). Кроме того, приглашения к обмену мгновенными сообщениями могут быть блокированы, если пользователь выбирает блокировку всех мгновенных сообщений от пользователей, не входящих в его список **Разрешить**.</span><span class="sxs-lookup"><span data-stu-id="cc648-p106">In the case of IM invitations, the response depends on the client software. The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists). Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cc648-130">Политики управления доступом пользователей общедоступных служб можно настроить даже при отсутствии федерации в организации.</span><span class="sxs-lookup"><span data-stu-id="cc648-130">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="cc648-131">Но настроенные политики действуют только при включенных федеративных отношениях для организации.</span><span class="sxs-lookup"><span data-stu-id="cc648-131">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="cc648-132">Подробнее о включении Федерации можно узнать в статье <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Включение и отключение удаленного доступа пользователей в Lync Server 2013</A> в документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="cc648-132">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="cc648-133">Кроме того, если указать политику пользователя для управления доступом пользователей с доступом Public, политика применяется только к пользователям, для которых включена Lync Server и настроено на использование политики.</span><span class="sxs-lookup"><span data-stu-id="cc648-133">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="cc648-134">Сведения об указании общедоступных пользователей, которые могут входить на сервер Lync Server, приведены в статье <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Назначение политики доступа внешних пользователей для пользователя с включенной поддержкой Lync в Lync Server 2013</A> в документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="cc648-134">For details about specifying public users that can sign in to Lync Server, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<span data-ttu-id="cc648-135">Для настройки политики, поддерживающей доступ пользователей одного или нескольких общедоступных поставщиков услуг обмена мгновенными сообщениями, используется следующая процедура.</span><span class="sxs-lookup"><span data-stu-id="cc648-135">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="cc648-136">Настройка политики внешнего доступа для поддержки доступа пользователей общедоступных служб</span><span class="sxs-lookup"><span data-stu-id="cc648-136">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="cc648-137">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="cc648-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cc648-138">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cc648-138">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cc648-139">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cc648-139">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cc648-140">На левой панели навигации щелкните **Внешний доступ пользователей**, затем щелкните **Политика внешнего доступа**.</span><span class="sxs-lookup"><span data-stu-id="cc648-140">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="cc648-141">На странице **Политика внешнего доступа** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="cc648-141">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="cc648-142">Чтобы настроить глобальную политику для поддержки доступа пользователей общедоступных служб, щелкните глобальную политику, щелкните **Изменить**, а затем щелкните **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="cc648-142">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="cc648-p109">Чтобы создать новую политику сайта, щелкните **Создать**, затем щелкните **Политика сайта**. В разделе **Выбор сайта** щелкните подходящий сайт в списке и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cc648-p109">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="cc648-p110">Чтобы создать новую политику для пользователей, щелкните **Создать**, затем щелкните **Политика пользователей**. В окне **Создание политики внешнего доступа** задайте в поле **Имя** уникальное имя, показывающее область применения этой политики (например, **EnablePublicUsers** для пользовательской политики, разрешающей взаимодействие с пользователями общедоступных служб).</span><span class="sxs-lookup"><span data-stu-id="cc648-p110">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="cc648-147">Чтобы изменить существующую политику, щелкните ее в таблице, щелкните **Изменить**, затем **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="cc648-147">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="cc648-148">(Необязательно) Если необходимо добавить или изменить описание, укажите сведения для этой политики в пункте **Описание**.</span><span class="sxs-lookup"><span data-stu-id="cc648-148">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="cc648-149">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="cc648-149">Do one of the following:</span></span>
    
      - <span data-ttu-id="cc648-150">Чтобы разрешить для политики доступ пользователей общедоступных служб, установите флажок **Разрешить взаимодействие с незарегистрированными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="cc648-150">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="cc648-151">Чтобы запретить для политики доступ пользователей общедоступных служб, снимите флажок **Разрешить взаимодействие с незарегистрированными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="cc648-151">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="cc648-152">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cc648-152">Click **Commit**.</span></span>

<span data-ttu-id="cc648-153">Чтобы включить доступ пользователей общедоступных служб, необходимо также включить в организации поддержку федерации.</span><span class="sxs-lookup"><span data-stu-id="cc648-153">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="cc648-154">Дополнительные сведения: [Настройка политик для управления доступом федеративных пользователей в Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="cc648-154">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="cc648-155">В случае пользовательской политики, также необходимо настроить и применить политику к пользователям общедоступных служб, которым требуется разрешить совместную работу с пользователями общедоступных служб.</span><span class="sxs-lookup"><span data-stu-id="cc648-155">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> <span data-ttu-id="cc648-156">Дополнительные сведения см. [в разделе назначение политик для отдельных пользователей в Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span><span class="sxs-lookup"><span data-stu-id="cc648-156">For details, see [Assigning per-user policies in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cc648-157">См. также</span><span class="sxs-lookup"><span data-stu-id="cc648-157">See Also</span></span>


[<span data-ttu-id="cc648-158">Создание или изменение общедоступных федеративных поставщиков SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc648-158">Create or edit public SIP federated providers in Lync Server 2013</span></span>](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[<span data-ttu-id="cc648-159">Управление федеративными поставщиками SIP для Организации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc648-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

