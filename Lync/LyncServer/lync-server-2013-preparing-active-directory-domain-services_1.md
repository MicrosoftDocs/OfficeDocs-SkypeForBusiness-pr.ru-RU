---
title: 'Lync Server 2013: Подготовка доменных служб Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03436a59fa9fbab99608e4fa3b979e4802115ed1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="211c1-102">Подготовка доменных служб Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="211c1-102">Preparing Active Directory Domain Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="211c1-103">_**Последнее изменение темы:** 2014-02-19_</span><span class="sxs-lookup"><span data-stu-id="211c1-103">_**Topic Last Modified:** 2014-02-19_</span></span>

<span data-ttu-id="211c1-104">В Lync Server 2013 вы можете использовать мастер развертывания Lync Server для подготовки доменных служб Active Directory или напрямую использовать командлеты командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="211c1-104">In Lync Server 2013, you can use the Lync Server Deployment Wizard to prepare Active Directory Domain Services, or you can use Lync Server Management Shell cmdlets directly.</span></span> <span data-ttu-id="211c1-105">Кроме того, можно использовать программу командной строки ldifde.exe непосредственно в контроллерах доменов, как описывается ниже в данной статье.</span><span class="sxs-lookup"><span data-stu-id="211c1-105">You can also use the ldifde.exe command line tool directly on your domain controllers, as described later in this topic.</span></span>

<span data-ttu-id="211c1-106">Мастер развертывания Lync Server поможет вам выполнить все задачи по подготовке Active Directory.</span><span class="sxs-lookup"><span data-stu-id="211c1-106">The Lync Server Deployment Wizard guides you through each Active Directory preparation task.</span></span> <span data-ttu-id="211c1-107">Мастер развертывания выполняет командлеты командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="211c1-107">The Deployment Wizard runs Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="211c1-108">Это средство полезно для сред с одним доменом и топологией одного леса или другой аналогичной топологией.</span><span class="sxs-lookup"><span data-stu-id="211c1-108">This tool is useful for environments with a single domain and single forest topology, or other similar topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="211c1-109">Вы можете развернуть Lync Server в лесу или домене, где контроллеры домена выполняют 32-разрядные версии некоторых операционных систем (Дополнительные сведения см. в статье <A href="lync-server-2013-active-directory-infrastructure-requirements.md">требования к инфраструктуре Active Directory для Lync Server 2013</A>).</span><span class="sxs-lookup"><span data-stu-id="211c1-109">You can deploy Lync Server in a forest or domain where domain controllers run 32-bit versions of some operating systems (for details, see <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory infrastructure requirements for Lync Server 2013</A>).</span></span> <span data-ttu-id="211c1-110">Однако мастер развертывания Lync Server невозможно использовать для запуска схемы, леса и подготовки доменов в этих средах, так как мастер развертывания и вспомогательные файлы имеют только 64 бит.</span><span class="sxs-lookup"><span data-stu-id="211c1-110">However, you cannot use the Lync Server Deployment Wizard to run schema, forest, and domain preparation in these environments because the Deployment Wizard and supporting files are 64-bit only.</span></span> <span data-ttu-id="211c1-111">Вместо этого можно использовать Ldifde. exe и связанные LDF файлы на контроллере домена 32, чтобы подготовить схему, лес и домен.</span><span class="sxs-lookup"><span data-stu-id="211c1-111">Instead, you can use ldifde.exe and the associated .ldf files on a 32-bit domain controller to prepare the schema, forest and domain.</span></span> <span data-ttu-id="211c1-112">Ознакомьтесь с разделом "использование командлетов и LDIFDE. exe" Далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="211c1-112">See the section “Using Cmdlets and Ldifde.exe” later in this topic.</span></span>



</div>

<span data-ttu-id="211c1-113">Командлеты командной консоли Lync Server можно использовать для удаленного запуска задач или более сложных сред.</span><span class="sxs-lookup"><span data-stu-id="211c1-113">You can use Lync Server Management Shell cmdlets to run tasks remotely or for more complex environments.</span></span>

<div>

## <a name="active-directory-preparation-prerequisites"></a><span data-ttu-id="211c1-114">Необходимые условия для подготовки Active Directory</span><span class="sxs-lookup"><span data-stu-id="211c1-114">Active Directory Preparation Prerequisites</span></span>

<span data-ttu-id="211c1-115">Необходимо выполнить подготовительные действия Active Directory на компьютере под управлением Windows Server 2012, Windows Server 2012 R2 или Windows Server 2008 R2 с пакетом обновления 1 (64-разр).</span><span class="sxs-lookup"><span data-stu-id="211c1-115">You must run Active Directory preparation steps on a computer running Windows Server 2012, Windows Server 2012 R2, or Windows Server 2008 R2 with SP1 (64-bit).</span></span> <span data-ttu-id="211c1-116">Для подготовки Active Directory требуется командная консоль Lync Server и OCSCore.</span><span class="sxs-lookup"><span data-stu-id="211c1-116">Active Directory preparation requires Lync Server Management Shell and OCSCore.</span></span>

<span data-ttu-id="211c1-117">Для выполнения задач подготовки Active Directory необходимы следующие компоненты.</span><span class="sxs-lookup"><span data-stu-id="211c1-117">The following components are required to run Active Directory preparation tasks:</span></span>

  - <span data-ttu-id="211c1-118">Основные компоненты Lync Server (OCScore. msi)</span><span class="sxs-lookup"><span data-stu-id="211c1-118">Lync Server Core components (OCScore.msi)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="211c1-119">Если вы планируете использовать командную консоль Lync Server для подготовки Active Directory, необходимо сначала запустить мастер развертывания Lync Server, чтобы установить основные компоненты.</span><span class="sxs-lookup"><span data-stu-id="211c1-119">If you plan to use Lync Server Management Shell for Active Directory preparation, you must run the Lync Server Deployment Wizard first to install Core components.</span></span>

    
    </div>

  - <span data-ttu-id="211c1-120">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="211c1-120">Microsoft .NET Framework 4.5</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="211c1-121">Для Windows Server 2012 и Windows Server 2012 R2 вы устанавливаете и активизируете .NET Framework 4,5 с помощью диспетчера серверов.</span><span class="sxs-lookup"><span data-stu-id="211c1-121">For Windows Server 2012 and Windows Server 2012 R2, you install and activate .NET Framework 4.5 by using Server Manager.</span></span> <span data-ttu-id="211c1-122">Подробнее: "Microsoft .NET Framework 4,5" в <A href="lync-server-2013-additional-software-requirements.md">дополнительных требованиях к программному обеспечению для Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="211c1-122">For details, see "Microsoft .NET Framework 4.5" in <A href="lync-server-2013-additional-software-requirements.md">Additional software requirements for Lync Server 2013</A>.</span></span> <span data-ttu-id="211c1-123">Для Windows Server&nbsp;2008&nbsp;R2 Скачайте и установите <A href="http://www.microsoft.com/download/details.aspx?id=30653">.NET Framework 4,5</A> на веб-сайте Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="211c1-123">For Windows Server&nbsp;2008&nbsp;R2, download and install <A href="http://www.microsoft.com/download/details.aspx?id=30653">.Net Framework 4.5</A> from the Microsoft web site.</span></span>

    
    </div>

  - <span data-ttu-id="211c1-124">Средства удаленного администрирования сервера (RSAT).</span><span class="sxs-lookup"><span data-stu-id="211c1-124">Remote Server Administration Tools (RSAT)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="211c1-125">Некоторые средства RSAT необходимы, когда действия по подготовке Active Directory выполняются не в контроллере домена, а на рядовом сервере.</span><span class="sxs-lookup"><span data-stu-id="211c1-125">Some RSAT tools are required if you run Active Directory preparation steps on a member server rather than on a domain controller.</span></span> <span data-ttu-id="211c1-126">Установите оснастки AD DS и средства командной строки и модуль Active Directory для Windows PowerShell из узла AD DS and AD LDS Tools в диспетчере серверов.</span><span class="sxs-lookup"><span data-stu-id="211c1-126">Install the AD DS snap-ins and command-line tools and the Active Directory Module for Windows PowerShell from the AD DS and AD LDS Tools node in Server Manager.</span></span>

    
    </div>

  - <span data-ttu-id="211c1-127">Распространяемый комплект Microsoft Visual C++ 11.</span><span class="sxs-lookup"><span data-stu-id="211c1-127">Microsoft Visual C++ 11 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="211c1-p107">Программа установки предложит установить этот необходимый компонент, если он не был установлен ранее. Пакет вам поставляется, и не придется приобретать его отдельно.</span><span class="sxs-lookup"><span data-stu-id="211c1-p107">Setup prompts you to install this prerequisite if it is not already installed on the computer. The package is supplied for you, and you will not have to acquire it separately.</span></span>

    
    </div>

  - <span data-ttu-id="211c1-130">Windows PowerShell 3,0 (64-бит)</span><span class="sxs-lookup"><span data-stu-id="211c1-130">Windows PowerShell 3.0 (64-bit)</span></span>
    
    <span data-ttu-id="211c1-131">Для Windows Server 2012 и Windows Server 2012 R2 необходимо включить Windows PowerShell 3,0 в установку Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="211c1-131">For Windows Server 2012 and Windows Server 2012 R2, Windows PowerShell 3.0 should be included with your Lync Server 2013 installation.</span></span> <span data-ttu-id="211c1-132">Для Windows Server 2008 R2 необходимо установить или обновить Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="211c1-132">For Windows Server 2008 R2, you need to install or upgrade to Windows PowerShell 3.0.</span></span> <span data-ttu-id="211c1-133">Дополнительные сведения см в статье [Установка Windows PowerShell 3,0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)</span><span class="sxs-lookup"><span data-stu-id="211c1-133">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)</span></span>

</div>

<div>

## <a name="administrator-rights-and-roles"></a><span data-ttu-id="211c1-134">Права и роли администратора</span><span class="sxs-lookup"><span data-stu-id="211c1-134">Administrator Rights and Roles</span></span>

<span data-ttu-id="211c1-135">В следующей таблице приведены административные права и роли, которые необходимы для каждой задачи подготовки Active Directory.</span><span class="sxs-lookup"><span data-stu-id="211c1-135">The following table shows the administrative rights and roles required for each Active Directory preparation task.</span></span>

### <a name="user-rights-required-for-active-directory-preparation"></a><span data-ttu-id="211c1-136">Права пользователя, необходимые для подготовки Active Directory</span><span class="sxs-lookup"><span data-stu-id="211c1-136">User Rights Required for Active Directory Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="211c1-137">Procedure</span><span class="sxs-lookup"><span data-stu-id="211c1-137">Procedure</span></span></th>
<th><span data-ttu-id="211c1-138">Права или роли</span><span class="sxs-lookup"><span data-stu-id="211c1-138">Rights or roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="211c1-139">Подготовка схемы</span><span class="sxs-lookup"><span data-stu-id="211c1-139">Schema preparation</span></span></p></td>
<td><p><span data-ttu-id="211c1-140">Членство в группе администраторов схемы для корневого домена леса и права администратора для хозяина схемы</span><span class="sxs-lookup"><span data-stu-id="211c1-140">Member of Schema Admins group for the forest root domain and administrator rights on the schema master</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="211c1-141">Подготовка леса</span><span class="sxs-lookup"><span data-stu-id="211c1-141">Forest preparation</span></span></p></td>
<td><p><span data-ttu-id="211c1-142">Членство в группе администраторов предприятия для леса</span><span class="sxs-lookup"><span data-stu-id="211c1-142">Member of Enterprise Admins group for the forest</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="211c1-143">Подготовка домена</span><span class="sxs-lookup"><span data-stu-id="211c1-143">Domain preparation</span></span></p></td>
<td><p><span data-ttu-id="211c1-144">Членство в группе администраторов предприятия или в группе администраторов домена для конкретного домена</span><span class="sxs-lookup"><span data-stu-id="211c1-144">Member of Enterprise Admins or Domain Admins group for the specified domain</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a><span data-ttu-id="211c1-145">Командлеты подготовки Active Directory</span><span class="sxs-lookup"><span data-stu-id="211c1-145">Active Directory Preparation Cmdlets</span></span>

<span data-ttu-id="211c1-146">В следующей таблице сравниваются командлеты командной консоли Lync Server, которые используются для подготовки AD DS к командам командами LcsCmd, используемым для подготовки AD DS в Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="211c1-146">The following table compares the Lync Server Management Shell cmdlets used to prepare AD DS to the LcsCmd commands used to prepare AD DS in Microsoft Office Communications Server 2007 R2.</span></span>

### <a name="cmdlets-compared-to-lcscmd"></a><span data-ttu-id="211c1-147">Командлеты в сравнении с командами LcsCmd</span><span class="sxs-lookup"><span data-stu-id="211c1-147">Cmdlets Compared to LcsCmd</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="211c1-148">Командлеты</span><span class="sxs-lookup"><span data-stu-id="211c1-148">Cmdlets</span></span></th>
<th><span data-ttu-id="211c1-149">Командами LcsCmd</span><span class="sxs-lookup"><span data-stu-id="211c1-149">LcsCmd</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="211c1-150">Install — CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="211c1-150">Install-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="211c1-151">Lcscmd /forest /action:SchemaPrep /SchemaType:Server</span><span class="sxs-lookup"><span data-stu-id="211c1-151">Lcscmd /forest /action:SchemaPrep /SchemaType:Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="211c1-152">Get — CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="211c1-152">Get-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="211c1-153">Lcscmd /forest /action:CheckSchemaPrepState</span><span class="sxs-lookup"><span data-stu-id="211c1-153">Lcscmd /forest /action:CheckSchemaPrepState</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="211c1-154">Enable — CsAdForest</span><span class="sxs-lookup"><span data-stu-id="211c1-154">Enable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="211c1-155">Lcscmd /forest /action:ForestPrep</span><span class="sxs-lookup"><span data-stu-id="211c1-155">Lcscmd /forest /action:ForestPrep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="211c1-156">Disable — CsAdForest</span><span class="sxs-lookup"><span data-stu-id="211c1-156">Disable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="211c1-157">Lcscmd /forest /action:ForestUnprep</span><span class="sxs-lookup"><span data-stu-id="211c1-157">Lcscmd /forest /action:ForestUnprep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="211c1-158">Get — CsAdForest</span><span class="sxs-lookup"><span data-stu-id="211c1-158">Get-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="211c1-159">Lcscmd /forest /action:CheckForestPrepState</span><span class="sxs-lookup"><span data-stu-id="211c1-159">Lcscmd /forest /action:CheckForestPrepState</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="211c1-160">Enable — CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="211c1-160">Enable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="211c1-161">Lcscmd /domain /action:DomainPrep</span><span class="sxs-lookup"><span data-stu-id="211c1-161">Lcscmd /domain /action:DomainPrep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="211c1-162">Disable — CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="211c1-162">Disable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="211c1-163">Lcscmd /domain /action: DomainUnprep</span><span class="sxs-lookup"><span data-stu-id="211c1-163">Lcscmd /domain /action: DomainUnprep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="211c1-164">Get — CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="211c1-164">Get-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="211c1-165">Lcscmd /domain /action:CheckDomainPrepState</span><span class="sxs-lookup"><span data-stu-id="211c1-165">Lcscmd /domain /action:CheckDomainPrepState</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a><span data-ttu-id="211c1-166">Блокирование требований Active Directory</span><span class="sxs-lookup"><span data-stu-id="211c1-166">Locked Down Active Directory Requirements</span></span>

<span data-ttu-id="211c1-167">Если в вашей организации отключено наследование разрешений, или должны быть отключены разрешения авторизованного пользователя, то во время подготовки домена необходимо выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="211c1-167">If permissions inheritance is disabled or authenticated user permissions must be disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="211c1-168">Дополнительные сведения см [в статье Подготовка заблокированных доменных служб Active Directory в Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="211c1-168">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

</div>

<div>

## <a name="custom-container-permissions"></a><span data-ttu-id="211c1-169">Разрешения настраиваемых контейнеров</span><span class="sxs-lookup"><span data-stu-id="211c1-169">Custom Container Permissions</span></span>

<span data-ttu-id="211c1-170">Если в вашей организации вместо трех встроенных контейнеров ("Пользователи", "Компьютеры" и "Контроллеры доменов") используются настраиваемые контейнеры, то необходимо предоставить группе авторизованных пользователей доступ на чтение в этих настраиваемых контейнерах.</span><span class="sxs-lookup"><span data-stu-id="211c1-170">If your organization uses custom containers instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the custom containers for the Authenticated Users group.</span></span> <span data-ttu-id="211c1-171">Доступ на чтение в этих контейнерах необходим для подготовки домена.</span><span class="sxs-lookup"><span data-stu-id="211c1-171">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="211c1-172">Дополнительные сведения см. в статье [Подготовка доменов для Lync Server 2013](lync-server-2013-preparing-domains.md).</span><span class="sxs-lookup"><span data-stu-id="211c1-172">For details, see [Preparing domains for Lync Server 2013](lync-server-2013-preparing-domains.md).</span></span>

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a><span data-ttu-id="211c1-173">Использование командлетов и Ldifde.exe</span><span class="sxs-lookup"><span data-stu-id="211c1-173">Using Cmdlets and Ldifde.exe</span></span>

<span data-ttu-id="211c1-174">Этап **подготовки схемы** в мастере развертывания Lync Server и командлет **Install – CsAdServerSchema** расширяет схему Active Directory на контроллерах домена под управлением 64 разрядной операционной системы.</span><span class="sxs-lookup"><span data-stu-id="211c1-174">The **Prepare Schema** step in the Lync Server Deployment Wizard and the **Install-CsAdServerSchema** cmdlet extend the Active Directory schema on domain controllers running a 64-bit operating system.</span></span> <span data-ttu-id="211c1-175">Если требуется распространить схему Active Directory на контроллер домена с 32-разрядной операционной системой, можно выполнить командлет **Install-CsAdServerSchema** удаленно с рядового сервера (это рекомендуемый подход).</span><span class="sxs-lookup"><span data-stu-id="211c1-175">If you need to extend the Active Directory schema on a domain controller running a 32-bit operating system, you can run the **Install-CsAdServerSchema** cmdlet remotely from a member server (recommended approach).</span></span> <span data-ttu-id="211c1-176">Однако если требуется выполнить подготовку схемы непосредственно в контроллере домена, можно использовать программу Ldifde.exe для импорта файлов схемы.</span><span class="sxs-lookup"><span data-stu-id="211c1-176">If you need to run schema preparation directly on the domain controller, however, you can use the Ldifde.exe tool to import the schema files.</span></span> <span data-ttu-id="211c1-177">Программа Ldifde.exe поставляется с большинством версий операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="211c1-177">The Ldifde.exe tool comes with most versions of the Windows operating system.</span></span>

<span data-ttu-id="211c1-p112">Если импорт файлов схемы выполняется с помощью программы Ldifde.exe, то необходимо импортировать все файлы, независимо от того, выполняется ли миграция от предыдущей версии или чистая установка. Эти файлы необходимо импортировать в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="211c1-p112">If you use Ldifde.exe to import the schema files, you must import all four files, regardless of whether you are migrating from a previous version or performing a clean installation. You must import them in the following sequence:</span></span>

1.  <span data-ttu-id="211c1-180">Екстерналсчема. ldf</span><span class="sxs-lookup"><span data-stu-id="211c1-180">ExternalSchema.ldf</span></span>

2.  <span data-ttu-id="211c1-181">Серверсчема. ldf</span><span class="sxs-lookup"><span data-stu-id="211c1-181">ServerSchema.ldf</span></span>

3.  <span data-ttu-id="211c1-182">Бакккомпатсчема. ldf</span><span class="sxs-lookup"><span data-stu-id="211c1-182">BackCompatSchema.ldf</span></span>

4.  <span data-ttu-id="211c1-183">Версионсчема. ldf</span><span class="sxs-lookup"><span data-stu-id="211c1-183">VersionSchema.ldf</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="211c1-184">Эти четыре LDF-файла расположены в каталоге \Support\Schema установочного носителя или загрузки.</span><span class="sxs-lookup"><span data-stu-id="211c1-184">The four .ldf files are located in \Support\Schema directory of your installation media or download.</span></span>



</div>

<span data-ttu-id="211c1-185">Чтобы с помощью программы Ldifde.exe импортировать эти четыре файла схемы в контроллер домена, который является хозяином схемы, используйте следующий формат:</span><span class="sxs-lookup"><span data-stu-id="211c1-185">To use Ldifde.exe to import the four schema files on a domain controller that is the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

<span data-ttu-id="211c1-186">Например:</span><span class="sxs-lookup"><span data-stu-id="211c1-186">For example:</span></span>

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> <span data-ttu-id="211c1-p113">Параметр b следует использовать только в том случае, если вы вошли как другой пользователь. Подробные сведения о необходимых правах пользователя см. в разделе "Права и роли администратора" выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="211c1-p113">Use the b parameter only if you are logged in as a different user. For details about the required user rights, see the "Administrator Rights and Roles" section earlier in this topic.</span></span>



</div>

<span data-ttu-id="211c1-189">Чтобы с помощью программы Ldifde.exe импортировать эти четыре файла схемы в контроллер домена, который не является хозяином схемы, используйте следующий формат:</span><span class="sxs-lookup"><span data-stu-id="211c1-189">To use Ldifde.exe to import the four schema files on a domain controller that is not the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

<span data-ttu-id="211c1-190">Подробнее об использовании ldifde можно узнать в статье базы знаний Майкрософт 237677 "использование средства LDIFDE для импорта и экспорта объектов каталога в Active Directory" по адресу [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204).</span><span class="sxs-lookup"><span data-stu-id="211c1-190">For details about using Ldifde, see Microsoft Knowledge Base article 237677, "Using LDIFDE to import and export directory objects to Active Directory," at [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="211c1-191">Содержание</span><span class="sxs-lookup"><span data-stu-id="211c1-191">In This Section</span></span>

  - [<span data-ttu-id="211c1-192">Подготовка схемы Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="211c1-192">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)

  - [<span data-ttu-id="211c1-193">Подготовка леса для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="211c1-193">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)

  - [<span data-ttu-id="211c1-194">Подготовка доменов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="211c1-194">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

