---
title: 'Lync Server 2013: конфигурация политик для управления общим доступом пользователей'
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
ms.openlocfilehash: b348abcce00eb57988c7aa5184c0cfb5ea302adb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a><span data-ttu-id="dcbed-102">Конфигурация политик для управления общим доступом пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcbed-102">Configure policies to control public user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dcbed-103">_**Тема последнего изменения:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="dcbed-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="dcbed-104">Общедоступная служба обмена мгновенными сообщениями позволяет пользователям в вашей организации общаться с пользователями служб обмена мгновенными сообщениями, предоставляемыми поставщиками Интернет-сообщений, в том числе с помощью сети Windows\!Live, Yahoo и AOL.</span><span class="sxs-lookup"><span data-stu-id="dcbed-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live network of Internet services, Yahoo\!, and AOL.</span></span> <span data-ttu-id="dcbed-105">Вы настраиваете одну или несколько политик доступа внешних пользователей для управления совместным доступом пользователей с помощью внутренних пользователей Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dcbed-105">You configure one or more external user access policies to control whether public users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="dcbed-106">Общедоступная служба обмена мгновенными сообщениями — это дополнительный компонент, который основывается на конфигурации развертывания и пользователей.</span><span class="sxs-lookup"><span data-stu-id="dcbed-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="dcbed-107">Это также зависит от подготовки службы в общедоступном поставщике обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="dcbed-107">It also depends on the provisioning of the service at the public IM provider.</span></span> <span data-ttu-id="dcbed-108">Сведения о том, как подготовить развертывание для использования общедоступных поставщиков, можно найти в статье Руководство по подготовке службы подключения к общедоступным СООБЩЕНИЯм для Microsoft Lync Server, Office Communications Server и сервера Live Communications Server.[http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)</span><span class="sxs-lookup"><span data-stu-id="dcbed-108">For information on how to provision your deployment to use the public providers, see the “Public IM Connectivity Provisioning Guide for Microsoft Lync Server, Office Communications Server, and Live Communications Server” guide: [http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="dcbed-109">По состоянию на 1 сентября 2012, лицензия на подписку на общедоступные службы обмена мгновенными сообщениями в Microsoft Lync ("PIC усл") больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="dcbed-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="dcbed-110">Пользователи с активными лицензиями смогут продолжать использовать федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="dcbed-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="dcbed-111">Messenger, пока служба не отключается.</span><span class="sxs-lookup"><span data-stu-id="dcbed-111">Messenger until the service shut down date.</span></span> <span data-ttu-id="dcbed-112">Дата окончания жизненного цикла 2014 для AOL и Yahoo! в течение июня.</span><span class="sxs-lookup"><span data-stu-id="dcbed-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="dcbed-113">было объявлено.</span><span class="sxs-lookup"><span data-stu-id="dcbed-113">has been announced.</span></span> <span data-ttu-id="dcbed-114">Подробности можно найти <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="dcbed-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="dcbed-115">УСЛ PIC является лицензией на ежемесячную подписку для пользователей Lync Server или Office Communications Server, которая требуется для Федерации с помощью Yahoo!.</span><span class="sxs-lookup"><span data-stu-id="dcbed-115">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="dcbed-116">Messenger.</span><span class="sxs-lookup"><span data-stu-id="dcbed-116">Messenger.</span></span> <span data-ttu-id="dcbed-117">Возможность предоставления этой услуги корпорацией Майкрософт зависит от поддержки компании Yahoo!, основного соглашения, для которого выполняется обмотка.</span><span class="sxs-lookup"><span data-stu-id="dcbed-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="dcbed-118">В некоторых случаях Lync — это мощный инструмент для связи между организациями и людьми по всему миру.</span><span class="sxs-lookup"><span data-stu-id="dcbed-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="dcbed-119">Для интеграции с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств за пределами стандартной клиентской лицензии Lync.</span><span class="sxs-lookup"><span data-stu-id="dcbed-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="dcbed-120">В этот список будет добавлена Федерация Skype, благодаря чему пользователи Lync смогут общаться с сотнями миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="dcbed-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="dcbed-121">Чтобы получить доступ к сайту подготовки службы подключения к общедоступным службам обмена мгновенными сообщениями Microsoft Lync Server, используйте следующую ссылку:[http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)</span><span class="sxs-lookup"><span data-stu-id="dcbed-121">To access the Microsoft Lync Server Public IM Connectivity Provisioning site, use the following link: [http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)</span></span>

<span data-ttu-id="dcbed-122">Для управления доступом пользователей можно настроить политики на уровне Global, site и User.</span><span class="sxs-lookup"><span data-stu-id="dcbed-122">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="dcbed-123">Дополнительные сведения о типах политик, которые можно настроить, приведены в разделе [Настройка поддержки внешних пользователей в Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) в документации по развертыванию или документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="dcbed-123">For details about the types of policies that you can configure, see [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) in the Deployment documentation or the Planning documentation.</span></span> <span data-ttu-id="dcbed-124">Параметры политики сервера Lync Server, примененные на одном уровне политики, могут переопределять параметры, примененные на другом уровне политики.</span><span class="sxs-lookup"><span data-stu-id="dcbed-124">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="dcbed-125">Приоритет политики Lync Server: политика пользователей (наибольшее влияние) переопределяет политику сайта, а затем политика сайта переопределяет глобальную политику (наименее влияние).</span><span class="sxs-lookup"><span data-stu-id="dcbed-125">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="dcbed-126">То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.</span><span class="sxs-lookup"><span data-stu-id="dcbed-126">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="dcbed-127">В случае приглашения на обмен мгновенными сообщениями ответ зависит от клиентского программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="dcbed-127">In the case of IM invitations, the response depends on the client software.</span></span> <span data-ttu-id="dcbed-128">Запрос принимается только в том случае, если внешние отправители явным образом не блокируются пользователем с помощью настраиваемого правила (то есть в параметрах **разрешенных** и **заблокированных** списков пользователей).</span><span class="sxs-lookup"><span data-stu-id="dcbed-128">The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists).</span></span> <span data-ttu-id="dcbed-129">Кроме того, приглашения на обмен мгновенными сообщениями можно блокировать, если пользователь заблокирует все сообщения от пользователей, не включенных в список **разрешений** .</span><span class="sxs-lookup"><span data-stu-id="dcbed-129">Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dcbed-130">Вы можете настроить политики для управления доступом пользователей и даже в том случае, если вы не включили Федерацию для своей организации.</span><span class="sxs-lookup"><span data-stu-id="dcbed-130">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="dcbed-131">Тем не менее, настроенные политики действуют только в том случае, если включена Федерация для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="dcbed-131">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="dcbed-132">Дополнительные сведения о включении Федерации можно найти <A href="lync-server-2013-enable-or-disable-remote-user-access.md">в разделе Включение и отключение удаленного доступа пользователей в Lync Server 2013</A> в документации по развертыванию или документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="dcbed-132">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="dcbed-133">Кроме того, если указать политику пользователей для управления доступом пользователей, политика применяется только к пользователям, которые включены в Lync Server и настроены на использование политики.</span><span class="sxs-lookup"><span data-stu-id="dcbed-133">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="dcbed-134">Подробнее об указании общедоступных пользователей, которые могут входить на сервер Lync Server, можно узнать в разделе <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">назначение внешней политики доступа пользователю Lync на Lync server 2013</A> в документации по развертыванию или документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="dcbed-134">For details about specifying public users that can sign in to Lync Server, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<span data-ttu-id="dcbed-135">Чтобы настроить политику для поддержки доступа пользователей одного или нескольких общедоступных служб обмена мгновенными сообщениями, выполните описанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="dcbed-135">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="dcbed-136">Настройка политики внешнего доступа для поддержки общего доступа пользователей</span><span class="sxs-lookup"><span data-stu-id="dcbed-136">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="dcbed-137">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="dcbed-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dcbed-138">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dcbed-138">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dcbed-139">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="dcbed-139">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dcbed-140">На панели навигации слева выберите **внешний доступ для пользователей**и нажмите кнопку **Политика внешних доступа**.</span><span class="sxs-lookup"><span data-stu-id="dcbed-140">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="dcbed-141">На странице " **политика внешней доступа** " выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="dcbed-141">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="dcbed-142">Чтобы настроить глобальную политику для поддержки доступа пользователей Public, щелкните глобальную политику, нажмите кнопку **изменить**, а затем выберите пункт **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="dcbed-142">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="dcbed-143">Чтобы создать новую политику сайта, нажмите кнопку **создать**и выберите пункт **Политика сайта**.</span><span class="sxs-lookup"><span data-stu-id="dcbed-143">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="dcbed-144">В разделе **выберите сайт**выберите нужный сайт из списка и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dcbed-144">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="dcbed-145">Чтобы создать политику пользователя, нажмите кнопку **создать**и выберите пункт **Политика пользователя**.</span><span class="sxs-lookup"><span data-stu-id="dcbed-145">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="dcbed-146">В **новой политике внешнего доступа**Создайте уникальное имя в поле Name ( **имя** ), которое указывает политику пользователя (например, **енаблепубликусерс** для политики пользователя, которая позволяет использовать связь для общедоступных пользователей).</span><span class="sxs-lookup"><span data-stu-id="dcbed-146">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="dcbed-147">Чтобы изменить существующую политику, выберите соответствующую политику, указанную в таблице, и нажмите кнопку **изменить**, а затем выберите команду **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="dcbed-147">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="dcbed-148">Необязательно Если вы хотите добавить или изменить описание, укажите сведения о политике в **описании**.</span><span class="sxs-lookup"><span data-stu-id="dcbed-148">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="dcbed-149">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="dcbed-149">Do one of the following:</span></span>
    
      - <span data-ttu-id="dcbed-150">Чтобы разрешить доступ к политике общим пользователям, установите флажок **разрешить связь с общедоступными пользователями** .</span><span class="sxs-lookup"><span data-stu-id="dcbed-150">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="dcbed-151">Чтобы отключить общий доступ пользователей для политики, снимите флажок **разрешить связь с общедоступными пользователями** .</span><span class="sxs-lookup"><span data-stu-id="dcbed-151">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="dcbed-152">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="dcbed-152">Click **Commit**.</span></span>

<span data-ttu-id="dcbed-153">Для включения доступа Public User необходимо также включить поддержку Федерации в Организации.</span><span class="sxs-lookup"><span data-stu-id="dcbed-153">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="dcbed-154">Подробности можно найти [в разделе Настройка политик для управления доступом к федеративным пользователям в Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="dcbed-154">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="dcbed-155">Если это политика пользователя, необходимо также применить политику к общедоступным пользователям, которые должны быть доступны для совместной работы с общедоступными пользователями.</span><span class="sxs-lookup"><span data-stu-id="dcbed-155">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> <span data-ttu-id="dcbed-156">Подробнее смотрите в разделе [назначение политик для пользователей в Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span><span class="sxs-lookup"><span data-stu-id="dcbed-156">For details, see [Assigning per-user policies in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dcbed-157">См. также</span><span class="sxs-lookup"><span data-stu-id="dcbed-157">See Also</span></span>


[<span data-ttu-id="dcbed-158">Создание или изменение общедоступных федеративных поставщиков SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcbed-158">Create or edit public SIP federated providers in Lync Server 2013</span></span>](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[<span data-ttu-id="dcbed-159">Управление федеративными поставщиками SIP в организации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcbed-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

