---
title: Доступ к сайту подготовки общедоступной службы обмена мгновенными сообщениями Lync Server
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
ms.openlocfilehash: e640e227ab15c19e48ed3dc06e4b7b482ab7b3a3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a><span data-ttu-id="9e65a-102">Доступ к сайту предоставления общедоступной службы обмена мгновенными сообщениями Lync Server с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e65a-102">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e65a-103">_**Последнее изменение темы:** 2019-03-22_</span><span class="sxs-lookup"><span data-stu-id="9e65a-103">_**Topic Last Modified:** 2019-03-22_</span></span>

<span data-ttu-id="9e65a-104">Процесс подготовки к подключению Lync и Skype изменился по сравнению с предыдущими методами подготовки PIC.</span><span class="sxs-lookup"><span data-stu-id="9e65a-104">The provisioning process for Lync-Skype connectivity has changed, as compared to previous PIC provisioning methods.</span></span> <span data-ttu-id="9e65a-105">Для завершения процесса подготовки может потребоваться до тридцати дней.</span><span class="sxs-lookup"><span data-stu-id="9e65a-105">This provisioning process can take up to thirty days to complete.</span></span> <span data-ttu-id="9e65a-106">Рекомендуется сначала запустить этот процесс перед выполнением остальных действий, описанных в этом документе.</span><span class="sxs-lookup"><span data-stu-id="9e65a-106">We recommend that you start this process first, prior to completing the remaining steps in this document.</span></span> <span data-ttu-id="9e65a-107">После завершения подготовки Lync-Skype для вашей учетной записи учетная запись активируется, и соответствующие пользователи могут включить общедоступную службу обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="9e65a-107">After the Lync-Skype provisioning process is completed for your account, the account is activated and your eligible users are enabled for public IM connectivity.</span></span>

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a><span data-ttu-id="9e65a-108">Чтобы подготовить Lync для подключения к Skype, необходимы следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="9e65a-108">To provision Lync-Skype connectivity, you need the following information:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="9e65a-109">Номер договора корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="9e65a-109">Microsoft Agreement Number</span></span></p></li>
<li><p><span data-ttu-id="9e65a-110">Полное доменное имя службы пограничного доступа (FQDN)</span><span class="sxs-lookup"><span data-stu-id="9e65a-110">Access Edge service fully qualified domain name (FQDN)</span></span></p></li>
<li><p><span data-ttu-id="9e65a-111">Домены протокола SIP</span><span class="sxs-lookup"><span data-stu-id="9e65a-111">Session Initiation Protocol (SIP) domain(s)</span></span></p></li>
<li><p><span data-ttu-id="9e65a-112">Любые дополнительные полные доменные имена для службы пограничного доступа</span><span class="sxs-lookup"><span data-stu-id="9e65a-112">Any additional Access Edge service FQDNs</span></span></p></li>
<li><p><span data-ttu-id="9e65a-113">Контактные данные</span><span class="sxs-lookup"><span data-stu-id="9e65a-113">Contact information</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9e65a-114">Начиная с апреля 2019, мы будем останавливать сбор и хранение контактных данных для клиентов, подготовленных для Федерации Skype через веб-сайт pic.lync.com.</span><span class="sxs-lookup"><span data-stu-id="9e65a-114">Beginning in April 2019, we will stop the collection and retention of contact information for customers who are provisioned for Skype Federation via the pic.lync.com website.</span></span> <span data-ttu-id="9e65a-115">Это изменение состоит в том, чтобы система подготовки pic.lync.com придерживается политик конфиденциальности корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9e65a-115">This change is being made to ensure that the pic.lync.com provisioning system adheres to Microsoft privacy policies.</span></span> 

<span data-ttu-id="9e65a-116">После того как это изменение будет продолжено, мы больше не сможете предоставлять обновления электронной почты по незавершенным изменениям подготовки.</span><span class="sxs-lookup"><span data-stu-id="9e65a-116">Once this change goes live, we will no longer be able to provide email updates on pending provisioning changes.</span></span> <span data-ttu-id="9e65a-117">Изменения подготовки PIC обычно завершаются в течение 24-48 часов после ввода.</span><span class="sxs-lookup"><span data-stu-id="9e65a-117">PIC provisioning changes typically complete within 24-48 hours after being entered.</span></span> <span data-ttu-id="9e65a-118">Если у вас по-прежнему возникают проблемы с федерациями Skype 48 часов после отправки запроса на подготовку, обратитесь в службу технической поддержки Майкрософт для дальнейшего изучения.</span><span class="sxs-lookup"><span data-stu-id="9e65a-118">If you are still experiencing Skype Federation issues 48 hours after submitting a provisioning request, please engage Microsoft Technical Support to investigate further.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e65a-119">В рамках этого изменения все ранее введенные контактные данные будут удалены из нашей системы на конец апреля 2019.</span><span class="sxs-lookup"><span data-stu-id="9e65a-119">As part of this change, all previously entered contact information will be purged from our system by the end of April, 2019.</span></span>

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a><span data-ttu-id="9e65a-120">Чтобы начать процесс подготовки к работе с Lync — Skype:</span><span class="sxs-lookup"><span data-stu-id="9e65a-120">To initiate the provisioning process for Lync-Skype connectivity:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="9e65a-121">Войдите на веб-сайт <strong>https://pic.lync.com</strong>, используя идентификатор Microsoft Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="9e65a-121">Sign in to the website, <strong>https://pic.lync.com</strong>, using your Microsoft Windows Live ID.</span></span></p></li>
<li><p><span data-ttu-id="9e65a-122">Выберите тип соглашения о лицензировании Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9e65a-122">Select the Microsoft licensing agreement type.</span></span></p></li>
<li><p><span data-ttu-id="9e65a-123">Установите флажок, чтобы проверить, что у вас есть права на чтение и принятие продукта для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9e65a-123">Select the check box, verifying that you have read and accept the Product Use Rights for Lync Server.</span></span></p></li>
<li><p><span data-ttu-id="9e65a-124">На странице " <strong>Запуск запроса на подготовку</strong> " щелкните соответствующую ссылку, чтобы инициировать запрос на подготовку:</span><span class="sxs-lookup"><span data-stu-id="9e65a-124">On the <strong>Initiate a Provisioning Request</strong> page, click the appropriate link to initiate a provisioning request:</span></span></p></li>
<li><p><span data-ttu-id="9e65a-125">На странице <strong>Указание сведений о подготовке</strong> введите <strong>полное доменное имя службы пограничного доступа</strong>.</span><span class="sxs-lookup"><span data-stu-id="9e65a-125">On the <strong>Specify Provisioning Information</strong> page, enter the <strong>Access Edge service FQDN</strong>.</span></span> <span data-ttu-id="9e65a-126">Например, <strong>SIP.contoso.com</strong>.</span><span class="sxs-lookup"><span data-stu-id="9e65a-126">For example, <strong>sip.contoso.com</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="9e65a-127">По истечении 1 июля для продолжения работы Майкрософт дополнительно требуется 2017, чтобы у пользователей было развернуто DNS SRV-запись Федерации для общедоступного подключения к службе обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="9e65a-127">After July 1st, 2017 Microsoft will additionally require customers have the Federation DNS SRV record deployed for Public IM connectivity to continue to work.</span></span>

</li>
<li><p><span data-ttu-id="9e65a-128">Введите по крайней мере одно имя домена SIP, а затем нажмите кнопку <strong>Добавить</strong>.</span><span class="sxs-lookup"><span data-stu-id="9e65a-128">Enter at least one or more SIP domain names, and then click <strong>Add</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="9e65a-129">Для завершения процесса подготовки необходимы по крайней мере один пограничный сервер доступа и один домен SIP.</span><span class="sxs-lookup"><span data-stu-id="9e65a-129">At least one Access Edge server and one SIP domain are required to complete the provisioning process.</span></span> <span data-ttu-id="9e65a-130">Домен SIP и пограничный сервер доступа должны быть активны, функционировать и доступны в сети.</span><span class="sxs-lookup"><span data-stu-id="9e65a-130">The SIP domain and the Access Edge server must be active, functioning, and reachable on the network.</span></span>

</li>
<li><p><span data-ttu-id="9e65a-131">В списке <strong>поставщиков общедоступных служб обмена мгновенными сообщениями</strong>выберите <strong>Skype</strong> и нажмите кнопку <strong>Далее</strong> , чтобы добавить контактную информацию и отправить запрос на подготовку.</span><span class="sxs-lookup"><span data-stu-id="9e65a-131">In the list of <strong>Public IM Service providers</strong>, select <strong>Skype,</strong> and click <strong>Next</strong> to add contact information, and submit the provisioning request.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9e65a-132">После отправки запроса на подготовку может пройти до 30 дней, чтобы учетная запись была активирована и пользователи могли включать общедоступные службы обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="9e65a-132">After the provisioning request has been submitted, it can take up to 30 days for the account to activate and for users to be enabled for public IM connectivity.</span></span>

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a><span data-ttu-id="9e65a-133">Включение Федерации и общедоступной службы обмена мгновенными сообщениями (PIC)</span><span class="sxs-lookup"><span data-stu-id="9e65a-133">Enabling Federation and Public IM Connectivity (PIC)</span></span>

<span data-ttu-id="9e65a-134">После отправки запроса на подготовку можно сосредоточиться на среде Lync Server и задачах администрирования, необходимых для настройки подключения Lync — Skype.</span><span class="sxs-lookup"><span data-stu-id="9e65a-134">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="9e65a-135">В этом разделе предполагается, что администратор Lync Server развернул Lync Server и настроил внешний доступ.</span><span class="sxs-lookup"><span data-stu-id="9e65a-135">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="9e65a-136">Дополнительные сведения о настройке внешнего доступа для Lync Server приведены в разделе "Планирование доступа внешних пользователей" в разделе [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) "Планирование доступа внешних пользователей" в разделе [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378)"Планирование доступа внешних пользователей".</span><span class="sxs-lookup"><span data-stu-id="9e65a-136">For additional information on configuring external access for Lync Server, see "Planning for External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) and "Deploying External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378).</span></span>

<span data-ttu-id="9e65a-137">Чтобы подготовить среду Lync Server к подключению Lync — Skype, администратор Lync Server должен выполнить следующие три задачи:</span><span class="sxs-lookup"><span data-stu-id="9e65a-137">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="9e65a-138">1\.</span><span class="sxs-lookup"><span data-stu-id="9e65a-138">1\.</span></span> <span data-ttu-id="9e65a-139">Настройка Федерации и PIC</span><span class="sxs-lookup"><span data-stu-id="9e65a-139">Configure Federation and PIC</span></span>

<span data-ttu-id="9e65a-140">Для предоставления пользователям Skype возможности общаться с пользователями Lync в Организации требуется Федерация.</span><span class="sxs-lookup"><span data-stu-id="9e65a-140">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="9e65a-141">Общедоступная служба обмена мгновенными сообщениями (PIC) — это класс Федерации, который необходимо настроить, чтобы разрешить пользователям Lync общаться с пользователями Skype.</span><span class="sxs-lookup"><span data-stu-id="9e65a-141">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="9e65a-142">Федерация и PIC настраиваются с помощью панели управления Lync Server, показанной ниже.</span><span class="sxs-lookup"><span data-stu-id="9e65a-142">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="9e65a-143">Федерация PIC больше не поддерживается сервером Live Communications 2005 с пакетом обновления 1 (SP1) или Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9e65a-143">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="9e65a-144">Поддерживаемыми платформами для Федерации PIC являются Lync Server 2013, Lync Server 2010 и Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9e65a-144">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="9e65a-145">2\.</span><span class="sxs-lookup"><span data-stu-id="9e65a-145">2\.</span></span> <span data-ttu-id="9e65a-146">Настройка по крайней мере одной политики для поддержки федеративного доступа пользователей</span><span class="sxs-lookup"><span data-stu-id="9e65a-146">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="9e65a-147">С помощью панели управления Lync Server администратор должен настроить одну или несколько политик доступа внешних пользователей, чтобы определить, могут ли пользователи Skype совместно работать с внутренними пользователями Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9e65a-147">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="9e65a-148">3\.</span><span class="sxs-lookup"><span data-stu-id="9e65a-148">3\.</span></span> <span data-ttu-id="9e65a-149">Настройка параметров поставщика Skype PIC для Lync</span><span class="sxs-lookup"><span data-stu-id="9e65a-149">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="9e65a-150">С помощью командной консоли Lync Server администратор должен настроить политику клиента Lync для отображения Skype в качестве дополнительного поставщика PIC.</span><span class="sxs-lookup"><span data-stu-id="9e65a-150">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="9e65a-151">Пользователи служб подключения к общедоступным службам обмена мгновенными сообщениями не могут участвовать в обмене мгновенными сообщениями или конференциях в Организации, пока не будет настроена хотя бы одна политика (шаг 2, ранее в этой процедуре) для поддержки подключения к общедоступным системам обмена мгновенными сообщения</span><span class="sxs-lookup"><span data-stu-id="9e65a-151">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span><BR><span data-ttu-id="9e65a-152">Чтобы настроить федерацию и PIC, обратитесь к разделу "Включение или отключение Федерации и общедоступной службы обмена мгновенными сообщениями" по адресу <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>.</span><span class="sxs-lookup"><span data-stu-id="9e65a-152">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>.</span></span><BR><span data-ttu-id="9e65a-153">Чтобы настроить по крайней мере одну политику для поддержки федеративного доступа пользователей, обратитесь к разделу "Настройка политик для управления <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>общими пользователями".</span><span class="sxs-lookup"><span data-stu-id="9e65a-153">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>.</span></span>



</div>

1.  <span data-ttu-id="9e65a-154">На сервере переднего плана Lync Server откройте командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9e65a-154">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="9e65a-155">Выполните две следующие команды:</span><span class="sxs-lookup"><span data-stu-id="9e65a-155">Run the following two commands:</span></span>
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="9e65a-156">Если у вас еще нет поставщика PIC в среде и создается новый поставщик PIC, выполнять командлет <STRONG>Remove – CsPublicProvider</STRONG> не требуется.</span><span class="sxs-lookup"><span data-stu-id="9e65a-156">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="9e65a-157">Добавлено в Lync Server 2013 CU5 &amp; для настольных ПК Lync в Office 2013 SP1, Намедекоратионраутингдомаин и намедекоратионексклудеддомаинлист совершенствуют ситуацию, в которой пользователи Lync добавляют контакты Skype, необходимые для "украшения" доменов, отличных от Майкрософт, для идентификации и направления их в Skype (формат: User (contoso. com) @msn. com).</span><span class="sxs-lookup"><span data-stu-id="9e65a-157">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="9e65a-158">Эти новые параметры позволят автоматически форматировать введенные пользователем адреса в диалоговом окне "Добавление контакта Skype" с параметром Намедекоратионраутингдомаин (который должен иметь значение msn.com), если он не содержит домены в Намедекоратионексклудеддомаинлист ( в настоящее время мы можем поддерживать msn.com, live.com, Hotmail.com, outlook.com).</span><span class="sxs-lookup"><span data-stu-id="9e65a-158">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

        
        </div>

3.  <span data-ttu-id="9e65a-159">В клиенте Lync теперь можно выбрать Skype в качестве поставщика PIC и добавить клиент Skype, указав учетную запись Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9e65a-159">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="9e65a-160">Кроме того, пользователи Skype, которые выполнили слияние и выполнили вход с помощью учетной записи Майкрософт, могут отправлять запрос контакта пользователям Lync.</span><span class="sxs-lookup"><span data-stu-id="9e65a-160">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="9e65a-161">Дополнительные сведения об учетных записях Майкрософт [можно узнать в разделе что такое учетная запись Майкрософт?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span><span class="sxs-lookup"><span data-stu-id="9e65a-161">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="9e65a-162">Дополнительную информацию о добавлении клиентов в Lync можно узнать [в статье использование подключения Lync — Skype в Lync Server 2013 в качестве конечного пользователя](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span><span class="sxs-lookup"><span data-stu-id="9e65a-162">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>

4.  <span data-ttu-id="9e65a-163">Подробную информацию об изменении размещенных поставщиков можно найти в разделе "Создание или изменение размещенных федеративных [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065)поставщиков SIP" по адресу.</span><span class="sxs-lookup"><span data-stu-id="9e65a-163">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="9e65a-164">Это завершает задачи администрирования, которые необходимо выполнить на сервере.</span><span class="sxs-lookup"><span data-stu-id="9e65a-164">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="9e65a-165">Теперь вы можете настроить подключение Lync к Skype.</span><span class="sxs-lookup"><span data-stu-id="9e65a-165">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<div>

## <a name="additional-resources"></a><span data-ttu-id="9e65a-166">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="9e65a-166">Additional Resources</span></span>

[<span data-ttu-id="9e65a-167">Использование Lync — подключение Skype в Lync Server 2013 в качестве конечного пользователя</span><span class="sxs-lookup"><span data-stu-id="9e65a-167">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[<span data-ttu-id="9e65a-168">Руководство по подготовке для подключения Lync — Skype в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e65a-168">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

