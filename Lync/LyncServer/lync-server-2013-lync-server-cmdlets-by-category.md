---
title: 'Lync Server 2013: командлеты Lync Server по категориям'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 cmdlets by category
ms:assetid: 4ce274d7-b0ec-40b8-b85e-9a0613916ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398306(v=OCS.15)
ms:contentKeyID: 48184106
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c7a5e0b3fa81d6730caed1f4ce2f89adf0d7d96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-cmdlets-by-category"></a><span data-ttu-id="2455d-102">Командлеты Lync Server 2013 по категориям</span><span class="sxs-lookup"><span data-stu-id="2455d-102">Lync Server 2013 cmdlets by category</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2455d-103">_**Тема последнего изменения:** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="2455d-103">_**Topic Last Modified:** 2017-09-20_</span></span>

<span data-ttu-id="2455d-104">Microsoft Lync Server 2013 поставляется с практическими командлетами 550, разработанными специально для разрешения администраторам управления сервером Lync Server из командной строки.</span><span class="sxs-lookup"><span data-stu-id="2455d-104">Microsoft Lync Server 2013 ships with almost 550 cmdlets specifically designed to allow administrators to manage Lync Server from the command line.</span></span> <span data-ttu-id="2455d-105">Вы получите доступ к командлетам из командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2455d-105">You access the cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="2455d-106">Вы можете получить справку по командлету прямо из командной строки, введя команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="2455d-106">You can retrieve help on a cmdlet directly from the command line by typing a command similar to the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="2455d-107">Предыдущая команда извлечет все справочные материалы, доступные для командлета **New-ксвоицеполици** .</span><span class="sxs-lookup"><span data-stu-id="2455d-107">The preceding command will retrieve all the help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="2455d-108">Замените ссылку на **New-ксвоицеполици** именем командлета, для которого требуется получить справку.</span><span class="sxs-lookup"><span data-stu-id="2455d-108">Substitute the reference to **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>

<span data-ttu-id="2455d-109">Чтобы получить полный список командлетов, доступных для управления Microsoft Lync Server 2013, в командной строке оболочки Lync Server Management Shell введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2455d-109">To retrieve a full list of cmdlets available for managing Microsoft Lync Server 2013, type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Command * -Module Lync -CommandType cmdlet

<span data-ttu-id="2455d-110">Если вы не знаете, какие командлеты вам нужны, мы также предоставили список командлетов и их справочные разделы.</span><span class="sxs-lookup"><span data-stu-id="2455d-110">If you are unsure which cmdlets you need, we have also provided a categorized list of cmdlets and their help topics.</span></span> <span data-ttu-id="2455d-111">Вы обнаружите, что некоторые командлеты отображаются в нескольких категориях, которые были намеренно применены к нескольким областям продукта.</span><span class="sxs-lookup"><span data-stu-id="2455d-111">You will find that some of the cmdlets show up in more than one category, which was intentional as they apply to multiple areas of the product.</span></span> <span data-ttu-id="2455d-112">Ниже приведен список категорий.</span><span class="sxs-lookup"><span data-stu-id="2455d-112">The following is a list of categories:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="2455d-113">Справочник по командлетам Skype для бизнеса перенесен на веб-сайт docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="2455d-113">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="2455d-114">По представленным ниже ссылкам вы можете перейти на новую страницу портала docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="2455d-114">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="2455d-115">Теперь весь контент предлагается с открытым исходным кодом и доступен в сообществе GitHub.</span><span class="sxs-lookup"><span data-stu-id="2455d-115">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="2455d-116">Хотите принять участие в работе с ним?</span><span class="sxs-lookup"><span data-stu-id="2455d-116">Interested in contributing?</span></span> <span data-ttu-id="2455d-117">Ознакомьтесь с ФАЙЛОМ README в репозитории здесь:<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="2455d-117">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2455d-118">Содержание</span><span class="sxs-lookup"><span data-stu-id="2455d-118">In This Section</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2455d-119"><a href="lync-server-2013-user-management-cmdlets.md">Командлеты управления пользователями в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2455d-119"><a href="lync-server-2013-user-management-cmdlets.md">User management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2455d-120"><a href="lync-server-2013-voice-application-cmdlets.md">Командлеты голосовых приложений в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2455d-120"><a href="lync-server-2013-voice-application-cmdlets.md">Voice application cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2455d-121"><a href="lync-server-2013-client-management-cmdlets.md">Командлеты управления клиентом в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2455d-121"><a href="lync-server-2013-client-management-cmdlets.md">Client management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2455d-122"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Дополнительные командлеты для корпоративных голосовых команд в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2455d-122"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Advanced Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2455d-123"><a href="lync-server-2013-im-and-presence-cmdlets.md">Командлеты для обмена мгновенными сообщениями и присутствия в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2455d-123"><a href="lync-server-2013-im-and-presence-cmdlets.md">IM and presence cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2455d-124"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">Командлеты подключения PSTN в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2455d-124"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">PSTN connectivity cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2455d-125"><a href="lync-server-2013-conferencing-cmdlets.md">Командлеты конференц-связи в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2455d-125"><a href="lync-server-2013-conferencing-cmdlets.md">Conferencing cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2455d-126"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Командлеты для телефонов и устройств в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2455d-126"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Phones and devices cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2455d-127"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Командлеты инфраструктуры и развертывания в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2455d-127"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Infrastructure and deployment cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2455d-128"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Командлеты миграции и сосуществования в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2455d-128"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Migration and coexistence cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2455d-129"><a href="lync-server-2013-security-cmdlets.md">Командлеты безопасности в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2455d-129"><a href="lync-server-2013-security-cmdlets.md">Security cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2455d-130"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Командлеты конфигурации оболочки Lync Server Management Shell в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2455d-130"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync Server Management Shell configuration cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2455d-131"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Командлеты серверных ролей и служб в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2455d-131"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Server roles and services cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2455d-132"><a href="lync-server-2013-mobility-cmdlets.md">Командлеты для мобильных устройств в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2455d-132"><a href="lync-server-2013-mobility-cmdlets.md">Mobility cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2455d-133"><a href="lync-server-2013-application-management-cmdlets.md">Командлеты управления приложениями в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2455d-133"><a href="lync-server-2013-application-management-cmdlets.md">Application management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2455d-134"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Командлеты сервера сохраняемого чата в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2455d-134"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Persistent Chat Server cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2455d-135"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Командлеты интеграции и внешнего доступа в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2455d-135"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Federation and external access cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2455d-136"><a href="lync-server-2013-centralized-logging-cmdlets.md">Командлеты централизованного ведения журналов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2455d-136"><a href="lync-server-2013-centralized-logging-cmdlets.md">Centralized Logging cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2455d-137"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Командлеты для корпоративных голосовых команд в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2455d-137"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2455d-138">См. также</span><span class="sxs-lookup"><span data-stu-id="2455d-138">See Also</span></span>


[<span data-ttu-id="2455d-139">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="2455d-139">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

