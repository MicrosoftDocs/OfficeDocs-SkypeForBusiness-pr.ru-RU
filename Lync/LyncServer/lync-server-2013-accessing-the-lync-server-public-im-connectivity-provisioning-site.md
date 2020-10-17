---
title: Доступ к сайту подготовки общедоступной службы обмена мгновенными сообщениями Lync Server
description: Доступ к сайту подготовки общедоступной службы обмена мгновенными сообщениями Lync Server.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing the Lync Server public IM connectivity provisioning site
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440174(v=OCS.15)
ms:contentKeyID: 57793364
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e12916b12de1ef3a3f990c6bee54c312ba6c1992
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571135"
---
# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a><span data-ttu-id="46519-103">Доступ к сайту предоставления общедоступной службы обмена мгновенными сообщениями Lync Server с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46519-103">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46519-104">_**Последнее изменение темы:** 2019-03-22_</span><span class="sxs-lookup"><span data-stu-id="46519-104">_**Topic Last Modified:** 2019-03-22_</span></span>

<span data-ttu-id="46519-105">Процесс подготовки к подключению к Lync-Skype изменился по сравнению с предыдущими методами подготовки PIC.</span><span class="sxs-lookup"><span data-stu-id="46519-105">The provisioning process for Lync-Skype connectivity has changed, as compared to previous PIC provisioning methods.</span></span> <span data-ttu-id="46519-106">Для завершения процесса подготовки может потребоваться до тридцати дней.</span><span class="sxs-lookup"><span data-stu-id="46519-106">This provisioning process can take up to thirty days to complete.</span></span> <span data-ttu-id="46519-107">Рекомендуется сначала запустить этот процесс перед выполнением остальных действий, описанных в этом документе.</span><span class="sxs-lookup"><span data-stu-id="46519-107">We recommend that you start this process first, prior to completing the remaining steps in this document.</span></span> <span data-ttu-id="46519-108">После завершения процесса подготовки Lync-Skype для учетной записи учетная запись активируется, и соответствующие пользователи могут иметь доступ к общедоступной службе обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="46519-108">After the Lync-Skype provisioning process is completed for your account, the account is activated and your eligible users are enabled for public IM connectivity.</span></span>

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a><span data-ttu-id="46519-109">Для подготовки подключения к Lync-Skype необходимы следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="46519-109">To provision Lync-Skype connectivity, you need the following information:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="46519-110">Номер договора корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="46519-110">Microsoft Agreement Number</span></span></p></li>
<li><p><span data-ttu-id="46519-111">Полное доменное имя службы пограничного доступа (FQDN)</span><span class="sxs-lookup"><span data-stu-id="46519-111">Access Edge service fully qualified domain name (FQDN)</span></span></p></li>
<li><p><span data-ttu-id="46519-112">Домены протокола SIP</span><span class="sxs-lookup"><span data-stu-id="46519-112">Session Initiation Protocol (SIP) domain(s)</span></span></p></li>
<li><p><span data-ttu-id="46519-113">Любые дополнительные полные доменные имена для службы пограничного доступа</span><span class="sxs-lookup"><span data-stu-id="46519-113">Any additional Access Edge service FQDNs</span></span></p></li>
<li><p><span data-ttu-id="46519-114">Контактные данные</span><span class="sxs-lookup"><span data-stu-id="46519-114">Contact information</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>

<span data-ttu-id="46519-115">Начиная с апреля 2019, мы будем останавливать сбор и хранение контактных данных для клиентов, подготовленных для Федерации Skype через веб-сайт pic.lync.com.</span><span class="sxs-lookup"><span data-stu-id="46519-115">Beginning in April 2019, we will stop the collection and retention of contact information for customers who are provisioned for Skype Federation via the pic.lync.com website.</span></span> <span data-ttu-id="46519-116">Это изменение состоит в том, чтобы система подготовки pic.lync.com придерживается политик конфиденциальности корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="46519-116">This change is being made to ensure that the pic.lync.com provisioning system adheres to Microsoft privacy policies.</span></span> 

<span data-ttu-id="46519-117">После того как это изменение будет продолжено, мы больше не сможете предоставлять обновления электронной почты по незавершенным изменениям подготовки.</span><span class="sxs-lookup"><span data-stu-id="46519-117">Once this change goes live, we will no longer be able to provide email updates on pending provisioning changes.</span></span> <span data-ttu-id="46519-118">Изменения подготовки PIC обычно завершаются в течение 24-48 часов после ввода.</span><span class="sxs-lookup"><span data-stu-id="46519-118">PIC provisioning changes typically complete within 24-48 hours after being entered.</span></span> <span data-ttu-id="46519-119">Если у вас по-прежнему возникают проблемы с федерациями Skype 48 часов после отправки запроса на подготовку, обратитесь в службу технической поддержки Майкрософт для дальнейшего изучения.</span><span class="sxs-lookup"><span data-stu-id="46519-119">If you are still experiencing Skype Federation issues 48 hours after submitting a provisioning request, please engage Microsoft Technical Support to investigate further.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="46519-120">В рамках этого изменения все ранее введенные контактные данные будут удалены из нашей системы на конец апреля 2019.</span><span class="sxs-lookup"><span data-stu-id="46519-120">As part of this change, all previously entered contact information will be purged from our system by the end of April, 2019.</span></span>

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a><span data-ttu-id="46519-121">Чтобы инициировать процесс подготовки к подключению к Lync-Skype:</span><span class="sxs-lookup"><span data-stu-id="46519-121">To initiate the provisioning process for Lync-Skype connectivity:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="46519-122">Войдите на веб-сайт, <strong>https://pic.lync.com</strong> используя идентификатор Microsoft Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="46519-122">Sign in to the website, <strong>https://pic.lync.com</strong>, using your Microsoft Windows Live ID.</span></span></p></li>
<li><p><span data-ttu-id="46519-123">Выберите тип соглашения о лицензировании Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="46519-123">Select the Microsoft licensing agreement type.</span></span></p></li>
<li><p><span data-ttu-id="46519-124">Установите флажок, чтобы проверить, что у вас есть права на чтение и принятие продукта для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="46519-124">Select the check box, verifying that you have read and accept the Product Use Rights for Lync Server.</span></span></p></li>
<li><p><span data-ttu-id="46519-125">На странице " <strong>Запуск запроса на подготовку</strong> " щелкните соответствующую ссылку, чтобы инициировать запрос на подготовку:</span><span class="sxs-lookup"><span data-stu-id="46519-125">On the <strong>Initiate a Provisioning Request</strong> page, click the appropriate link to initiate a provisioning request:</span></span></p></li>
<li><p><span data-ttu-id="46519-126">На странице <strong>Указание сведений о подготовке</strong> введите <strong>полное доменное имя службы пограничного доступа</strong>.</span><span class="sxs-lookup"><span data-stu-id="46519-126">On the <strong>Specify Provisioning Information</strong> page, enter the <strong>Access Edge service FQDN</strong>.</span></span> <span data-ttu-id="46519-127">Например, <strong>SIP.contoso.com</strong>.</span><span class="sxs-lookup"><span data-stu-id="46519-127">For example, <strong>sip.contoso.com</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="46519-128">По истечении 1 июля для продолжения работы Майкрософт дополнительно требуется 2017, чтобы у пользователей было развернуто DNS SRV-запись Федерации для общедоступного подключения к службе обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="46519-128">After July 1st, 2017 Microsoft will additionally require customers have the Federation DNS SRV record deployed for Public IM connectivity to continue to work.</span></span>

</li>
<li><p><span data-ttu-id="46519-129">Введите по крайней мере одно имя домена SIP, а затем нажмите кнопку <strong>Добавить</strong>.</span><span class="sxs-lookup"><span data-stu-id="46519-129">Enter at least one or more SIP domain names, and then click <strong>Add</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="46519-130">Для завершения процесса подготовки необходимы по крайней мере один пограничный сервер доступа и один домен SIP.</span><span class="sxs-lookup"><span data-stu-id="46519-130">At least one Access Edge server and one SIP domain are required to complete the provisioning process.</span></span> <span data-ttu-id="46519-131">Домен SIP и пограничный сервер доступа должны быть активны, функционировать и доступны в сети.</span><span class="sxs-lookup"><span data-stu-id="46519-131">The SIP domain and the Access Edge server must be active, functioning, and reachable on the network.</span></span>

</li>
<li><p><span data-ttu-id="46519-132">В списке <strong>поставщиков общедоступных служб обмена мгновенными сообщениями</strong>выберите <strong>Skype</strong> и нажмите кнопку <strong>Далее</strong> , чтобы добавить контактную информацию и отправить запрос на подготовку.</span><span class="sxs-lookup"><span data-stu-id="46519-132">In the list of <strong>Public IM Service providers</strong>, select <strong>Skype,</strong> and click <strong>Next</strong> to add contact information, and submit the provisioning request.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


<span data-ttu-id="46519-133">После отправки запроса на подготовку может пройти до 30 дней, чтобы учетная запись была активирована и пользователи могли включать общедоступные службы обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="46519-133">After the provisioning request has been submitted, it can take up to 30 days for the account to activate and for users to be enabled for public IM connectivity.</span></span>

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a><span data-ttu-id="46519-134">Включение Федерации и общедоступной службы обмена мгновенными сообщениями (PIC)</span><span class="sxs-lookup"><span data-stu-id="46519-134">Enabling Federation and Public IM Connectivity (PIC)</span></span>

<span data-ttu-id="46519-135">После отправки запроса на подготовку можно сосредоточиться на среде Lync Server и задачах администрирования, необходимых для настройки подключения к Lync-Skype.</span><span class="sxs-lookup"><span data-stu-id="46519-135">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="46519-136">В этом разделе предполагается, что администратор Lync Server развернул Lync Server и настроил внешний доступ.</span><span class="sxs-lookup"><span data-stu-id="46519-136">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="46519-137">Дополнительные сведения о настройке внешнего доступа для Lync Server приведены в разделе "Планирование доступа внешних пользователей" в разделе "Планирование доступа внешних пользователей" в разделе "Планирование доступа внешних пользователей" [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378) .</span><span class="sxs-lookup"><span data-stu-id="46519-137">For additional information on configuring external access for Lync Server, see "Planning for External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) and "Deploying External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378).</span></span>

<span data-ttu-id="46519-138">Чтобы подготовить среду Lync Server для подключения к Lync-Skype, администратор Lync Server должен выполнить следующие три задачи:</span><span class="sxs-lookup"><span data-stu-id="46519-138">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="46519-139">1\.</span><span class="sxs-lookup"><span data-stu-id="46519-139">1\.</span></span> <span data-ttu-id="46519-140">Настройка Федерации и PIC</span><span class="sxs-lookup"><span data-stu-id="46519-140">Configure Federation and PIC</span></span>

<span data-ttu-id="46519-141">Для предоставления пользователям Skype возможности общаться с пользователями Lync в Организации требуется Федерация.</span><span class="sxs-lookup"><span data-stu-id="46519-141">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="46519-142">Общедоступная служба обмена мгновенными сообщениями (PIC) — это класс Федерации, который необходимо настроить, чтобы разрешить пользователям Lync общаться с пользователями Skype.</span><span class="sxs-lookup"><span data-stu-id="46519-142">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="46519-143">Федерация и PIC настраиваются с помощью панели управления Lync Server, показанной ниже.</span><span class="sxs-lookup"><span data-stu-id="46519-143">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="46519-144">Федерация PIC больше не поддерживается сервером Live Communications 2005 с пакетом обновления 1 (SP1) или Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="46519-144">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="46519-145">Поддерживаемыми платформами для Федерации PIC являются Lync Server 2013, Lync Server 2010 и Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="46519-145">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="46519-146">2\.</span><span class="sxs-lookup"><span data-stu-id="46519-146">2\.</span></span> <span data-ttu-id="46519-147">Настройка по крайней мере одной политики для поддержки федеративного доступа пользователей</span><span class="sxs-lookup"><span data-stu-id="46519-147">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="46519-148">С помощью панели управления Lync Server администратор должен настроить одну или несколько политик доступа внешних пользователей, чтобы определить, могут ли пользователи Skype совместно работать с внутренними пользователями Lync Server.</span><span class="sxs-lookup"><span data-stu-id="46519-148">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="46519-149">3\.</span><span class="sxs-lookup"><span data-stu-id="46519-149">3\.</span></span> <span data-ttu-id="46519-150">Настройка параметров поставщика Skype PIC для Lync</span><span class="sxs-lookup"><span data-stu-id="46519-150">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="46519-151">С помощью командной консоли Lync Server администратор должен настроить политику клиента Lync для отображения Skype в качестве дополнительного поставщика PIC.</span><span class="sxs-lookup"><span data-stu-id="46519-151">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="46519-152">Пользователи служб подключения к общедоступным службам обмена мгновенными сообщениями не могут участвовать в обмене мгновенными сообщениями или конференциях в Организации, пока не будет настроена хотя бы одна политика (шаг 2, ранее в этой процедуре) для поддержки подключения к общедоступным системам обмена мгновенными сообщения</span><span class="sxs-lookup"><span data-stu-id="46519-152">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span><BR><span data-ttu-id="46519-153">Чтобы настроить федерацию и PIC, обратитесь к разделу "Включение или отключение Федерации и общедоступной службы обмена мгновенными сообщениями" по адресу <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A> .</span><span class="sxs-lookup"><span data-stu-id="46519-153">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>.</span></span><BR><span data-ttu-id="46519-154">Чтобы настроить по крайней мере одну политику для поддержки федеративного доступа пользователей, обратитесь к разделу "Настройка политик для управления общими пользователями" <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A> .</span><span class="sxs-lookup"><span data-stu-id="46519-154">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>.</span></span>



</div>

1.  <span data-ttu-id="46519-155">На сервере переднего плана Lync Server откройте командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="46519-155">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="46519-156">Выполните две следующие команды:</span><span class="sxs-lookup"><span data-stu-id="46519-156">Run the following two commands:</span></span>
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="46519-157">Если у вас еще нет поставщика PIC в среде и создается новый поставщик PIC, выполнять командлет <STRONG>Remove – CsPublicProvider</STRONG> не требуется.</span><span class="sxs-lookup"><span data-stu-id="46519-157">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="46519-158">Добавлено в Lync Server 2013 CU5 для &amp; настольных ПК Lync в Office 2013 SP1, намедекоратионраутингдомаин и намедекоратионексклудеддомаинлист совершенствуют ситуацию, в которой пользователи Lync добавляют контакты Skype, необходимые для "украшения" доменов, отличных от Майкрософт, для идентификации и направления их в Skype (формат: User (contoso. com) @msn. com).</span><span class="sxs-lookup"><span data-stu-id="46519-158">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="46519-159">Эти новые параметры позволят автоматически форматировать введенные пользователем адреса в диалоговом окне "Добавление контакта Skype" с параметром Намедекоратионраутингдомаин (который должен иметь значение msn.com), если он не содержит домены в Намедекоратионексклудеддомаинлист (в настоящее время поддерживается поддержка msn.com, live.com, Hotmail.com, outlook.com).</span><span class="sxs-lookup"><span data-stu-id="46519-159">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

        
        </div>

3.  <span data-ttu-id="46519-160">В клиенте Lync теперь можно выбрать Skype в качестве поставщика PIC и добавить клиент Skype, указав учетную запись Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="46519-160">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="46519-161">Кроме того, пользователи Skype, которые выполнили слияние и выполнили вход с помощью учетной записи Майкрософт, могут отправлять запрос контакта пользователям Lync.</span><span class="sxs-lookup"><span data-stu-id="46519-161">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="46519-162">Дополнительные сведения об учетных записях Майкрософт [можно узнать в разделе что такое учетная запись Майкрософт?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span><span class="sxs-lookup"><span data-stu-id="46519-162">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="46519-163">Дополнительные сведения о добавлении клиентов в Lync можно узнать [в статье использование Lync-Skype подключения к Lync Server 2013 в качестве конечного пользователя](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span><span class="sxs-lookup"><span data-stu-id="46519-163">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>

4.  <span data-ttu-id="46519-164">Подробную информацию об изменении размещенных поставщиков можно найти в разделе "Создание или изменение размещенных федеративных поставщиков SIP" по адресу [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065) .</span><span class="sxs-lookup"><span data-stu-id="46519-164">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="46519-165">Это завершает задачи администрирования, которые необходимо выполнить на сервере.</span><span class="sxs-lookup"><span data-stu-id="46519-165">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="46519-166">Теперь вы можете настроить подключение к Lync-Skype.</span><span class="sxs-lookup"><span data-stu-id="46519-166">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<div>

## <a name="additional-resources"></a><span data-ttu-id="46519-167">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="46519-167">Additional Resources</span></span>

[<span data-ttu-id="46519-168">Использование Lync-Skype подключения в Lync Server 2013 в качестве конечного пользователя</span><span class="sxs-lookup"><span data-stu-id="46519-168">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[<span data-ttu-id="46519-169">Руководство по подготовке к Lync-Skype подключениям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46519-169">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

