---
title: 'Lync Server 2013: Включение подключения к Lync-Skype'
description: 'Lync Server 2013: Включение подключения к Lync-Skype.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Lync-Skype connectivity
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440170(v=OCS.15)
ms:contentKeyID: 57793361
ms.date: 12/16/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f31856299b05af7d6b8e934d6e9784d1571b7e29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558495"
---
# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="f85d7-103">Включение подключения к Lync-Skype в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f85d7-103">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f85d7-104">_**Последнее изменение темы:** 2014-12-16_</span><span class="sxs-lookup"><span data-stu-id="f85d7-104">_**Topic Last Modified:** 2014-12-16_</span></span>

<span data-ttu-id="f85d7-105">После отправки запроса на подготовку можно сосредоточиться на среде Lync Server и задачах администрирования, необходимых для настройки подключения к Lync-Skype.</span><span class="sxs-lookup"><span data-stu-id="f85d7-105">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="f85d7-106">В этом разделе предполагается, что администратор Lync Server развернул Lync Server и настроил внешний доступ.</span><span class="sxs-lookup"><span data-stu-id="f85d7-106">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="f85d7-107">Дополнительные сведения о настройке внешнего доступа для Lync Server приведены в статье [Планирование доступа внешних пользователей в Lync server 2013](lync-server-2013-planning-for-external-user-access.md) и [развертывание доступа внешних пользователей в Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="f85d7-107">For additional information on configuring external access for Lync Server, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

<span data-ttu-id="f85d7-108">Чтобы подготовить среду Lync Server для подключения к Lync-Skype, администратор Lync Server должен выполнить следующие три задачи:</span><span class="sxs-lookup"><span data-stu-id="f85d7-108">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="f85d7-109">1\.</span><span class="sxs-lookup"><span data-stu-id="f85d7-109">1\.</span></span> <span data-ttu-id="f85d7-110">Настройка Федерации и PIC</span><span class="sxs-lookup"><span data-stu-id="f85d7-110">Configure Federation and PIC</span></span>

<span data-ttu-id="f85d7-111">Для предоставления пользователям Skype возможности общаться с пользователями Lync в Организации требуется Федерация.</span><span class="sxs-lookup"><span data-stu-id="f85d7-111">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="f85d7-112">Общедоступная служба обмена мгновенными сообщениями (PIC) — это класс Федерации, который необходимо настроить, чтобы разрешить пользователям Lync общаться с пользователями Skype.</span><span class="sxs-lookup"><span data-stu-id="f85d7-112">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="f85d7-113">Федерация и PIC настраиваются с помощью панели управления Lync Server, показанной ниже.</span><span class="sxs-lookup"><span data-stu-id="f85d7-113">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<span data-ttu-id="f85d7-114">![Показ PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Показ PIC")</span><span class="sxs-lookup"><span data-stu-id="f85d7-114">![Showing PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Showing PIC")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f85d7-115">Федерация PIC больше не поддерживается сервером Live Communications 2005 с пакетом обновления 1 (SP1) или Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f85d7-115">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="f85d7-116">Поддерживаемыми платформами для Федерации PIC являются Lync Server 2013, Lync Server 2010 и Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f85d7-116">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="f85d7-117">2\.</span><span class="sxs-lookup"><span data-stu-id="f85d7-117">2\.</span></span> <span data-ttu-id="f85d7-118">Настройка по крайней мере одной политики для поддержки федеративного доступа пользователей</span><span class="sxs-lookup"><span data-stu-id="f85d7-118">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="f85d7-119">С помощью панели управления Lync Server администратор должен настроить одну или несколько политик доступа внешних пользователей, чтобы определить, могут ли пользователи Skype совместно работать с внутренними пользователями Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f85d7-119">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

<span data-ttu-id="f85d7-120">![Политики](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Политики")</span><span class="sxs-lookup"><span data-stu-id="f85d7-120">![Policies](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Policies")</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="f85d7-121">3\.</span><span class="sxs-lookup"><span data-stu-id="f85d7-121">3\.</span></span> <span data-ttu-id="f85d7-122">Настройка параметров поставщика Skype PIC для Lync</span><span class="sxs-lookup"><span data-stu-id="f85d7-122">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="f85d7-123">С помощью командной консоли Lync Server администратор должен настроить политику клиента Lync для отображения Skype в качестве дополнительного поставщика PIC.</span><span class="sxs-lookup"><span data-stu-id="f85d7-123">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f85d7-124">Пользователи поставщиков услуг общедоступных мгновенных сообщений не могут участвовать в обмене мгновенными сообщениями или аудио-и видеоконференциях в Организации до тех пор, пока не будет настроена хотя бы одна политика (шаг 2, ранее в этой процедуре) для поддержки подключения к общедоступным системам обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="f85d7-124">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or audio or video conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span>



</div>

1.  <span data-ttu-id="f85d7-125">Чтобы настроить федерацию и PIC, обратитесь к разделу "Включение или отключение Федерации и общедоступной службы обмена мгновенными сообщениями" по адресу [https://go.microsoft.com/fwlink/p/?LinkId=306063](https://go.microsoft.com/fwlink/p/?linkid=306063) .</span><span class="sxs-lookup"><span data-stu-id="f85d7-125">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at [https://go.microsoft.com/fwlink/p/?LinkId=306063](https://go.microsoft.com/fwlink/p/?linkid=306063).</span></span>

2.  <span data-ttu-id="f85d7-126">Чтобы настроить по крайней мере одну политику для поддержки федеративного доступа пользователей, обратитесь к разделу "Настройка политик для управления общими пользователями" [https://go.microsoft.com/fwlink/p/?LinkId=306064](https://go.microsoft.com/fwlink/p/?linkid=306064) .</span><span class="sxs-lookup"><span data-stu-id="f85d7-126">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at [https://go.microsoft.com/fwlink/p/?LinkId=306064](https://go.microsoft.com/fwlink/p/?linkid=306064).</span></span>

<span data-ttu-id="f85d7-127">**Изменение существующего поставщика услуг обмена сообщениями или Skype PIC и настройка его для Skype**</span><span class="sxs-lookup"><span data-stu-id="f85d7-127">**To edit an existing Messenger or Skype PIC provider and configure it for Skype**</span></span>

1.  <span data-ttu-id="f85d7-128">На сервере переднего плана Lync Server откройте командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f85d7-128">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="f85d7-129">Выполните две следующие команды:</span><span class="sxs-lookup"><span data-stu-id="f85d7-129">Run the following two commands:</span></span>
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f85d7-130">Если у вас еще нет поставщика PIC в среде и создается новый поставщик PIC, выполнять командлет <STRONG>Remove – CsPublicProvider</STRONG> не требуется.</span><span class="sxs-lookup"><span data-stu-id="f85d7-130">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f85d7-131">Добавлено в Lync Server 2013 CU5 для &amp; настольных ПК Lync в Office 2013 SP1, намедекоратионраутингдомаин и намедекоратионексклудеддомаинлист совершенствуют ситуацию, в которой пользователи Lync добавляют контакты Skype, необходимые для "украшения" доменов, отличных от Майкрософт, для идентификации и направления их в Skype (формат: User (contoso. com) @msn. com).</span><span class="sxs-lookup"><span data-stu-id="f85d7-131">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="f85d7-132">Эти новые параметры позволят автоматически форматировать введенные пользователем адреса в диалоговом окне "Добавление контакта Skype" с параметром Намедекоратионраутингдомаин (который должен иметь значение msn.com), если он не содержит домены в Намедекоратионексклудеддомаинлист (в настоящее время поддерживается поддержка msn.com, live.com, Hotmail.com, outlook.com).</span><span class="sxs-lookup"><span data-stu-id="f85d7-132">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

    
    </div>

3.  <span data-ttu-id="f85d7-133">В клиенте Lync теперь можно выбрать Skype в качестве поставщика PIC и добавить клиент Skype, указав учетную запись Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f85d7-133">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="f85d7-134">Кроме того, пользователи Skype, которые выполнили слияние и выполнили вход с помощью учетной записи Майкрософт, могут отправлять запрос контакта пользователям Lync.</span><span class="sxs-lookup"><span data-stu-id="f85d7-134">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="f85d7-135">Дополнительные сведения об учетных записях Майкрософт [можно узнать в разделе что такое учетная запись Майкрософт?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span><span class="sxs-lookup"><span data-stu-id="f85d7-135">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="f85d7-136">Дополнительные сведения о добавлении клиентов в Lync можно узнать [в статье использование Lync-Skype подключения к Lync Server 2013 в качестве конечного пользователя](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span><span class="sxs-lookup"><span data-stu-id="f85d7-136">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>
    
    <span data-ttu-id="f85d7-137">![Добавление контакта Skype](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Добавление контакта Skype")</span><span class="sxs-lookup"><span data-stu-id="f85d7-137">![Add Skype Contact](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Add Skype Contact")</span></span>

4.  <span data-ttu-id="f85d7-138">Подробную информацию об изменении размещенных поставщиков можно найти в разделе "Создание или изменение размещенных федеративных поставщиков SIP" по адресу [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065) .</span><span class="sxs-lookup"><span data-stu-id="f85d7-138">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="f85d7-139">Это завершает задачи администрирования, которые необходимо выполнить на сервере.</span><span class="sxs-lookup"><span data-stu-id="f85d7-139">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="f85d7-140">Теперь вы можете настроить подключение к Lync-Skype.</span><span class="sxs-lookup"><span data-stu-id="f85d7-140">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

