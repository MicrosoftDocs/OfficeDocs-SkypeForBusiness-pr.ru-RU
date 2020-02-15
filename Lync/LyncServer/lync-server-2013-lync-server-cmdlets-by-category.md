---
title: 'Lync Server 2013: командлеты Lync Server по категории'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 cmdlets by category
ms:assetid: 4ce274d7-b0ec-40b8-b85e-9a0613916ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398306(v=OCS.15)
ms:contentKeyID: 48184106
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d5db33e3d41bca0a3d14361b6d7bda254d43d19
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-cmdlets-by-category"></a><span data-ttu-id="4dd26-102">Командлеты Lync Server 2013 по категориям</span><span class="sxs-lookup"><span data-stu-id="4dd26-102">Lync Server 2013 cmdlets by category</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4dd26-103">_**Последнее изменение темы:** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="4dd26-103">_**Topic Last Modified:** 2017-09-20_</span></span>

<span data-ttu-id="4dd26-104">В Microsoft Lync Server 2013 поставляется почти 550 командлетов, специально разработанных, чтобы позволить администраторам управлять сервером Lync Server из командной строки.</span><span class="sxs-lookup"><span data-stu-id="4dd26-104">Microsoft Lync Server 2013 ships with almost 550 cmdlets specifically designed to allow administrators to manage Lync Server from the command line.</span></span> <span data-ttu-id="4dd26-105">Вы обращаетесь к командлетам из командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4dd26-105">You access the cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="4dd26-106">Вы можете получить справку по командлету непосредственно в командной строке, введя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4dd26-106">You can retrieve help on a cmdlet directly from the command line by typing a command similar to the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="4dd26-107">Предыдущая команда получает все доступные сведения справки для командлета **New-CsVoicePolicy**.</span><span class="sxs-lookup"><span data-stu-id="4dd26-107">The preceding command will retrieve all the help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="4dd26-108">Дополните  ссылку на **New-CsVoicePolicy** именем командлета, для которого вы хотите получить справку.</span><span class="sxs-lookup"><span data-stu-id="4dd26-108">Substitute the reference to **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>

<span data-ttu-id="4dd26-109">Чтобы получить полный список командлетов, доступных для управления Microsoft Lync Server 2013, введите в командной строке Командная консоль Lync Server следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4dd26-109">To retrieve a full list of cmdlets available for managing Microsoft Lync Server 2013, type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Command * -Module Lync -CommandType cmdlet

<span data-ttu-id="4dd26-p103">Если вы точно не знаете, какие командлеты вам нужны мы также предоставили упорядоченный по категориям список командлетов и соответствующих разделов справки. Вы обнаружите, что некоторые командлеты указаны в нескольких категориях, это сделано намеренно, так как они применяются в нескольких областях продукта. Ниже приведен список категорий:</span><span class="sxs-lookup"><span data-stu-id="4dd26-p103">If you are unsure which cmdlets you need, we have also provided a categorized list of cmdlets and their help topics. You will find that some of the cmdlets show up in more than one category, which was intentional as they apply to multiple areas of the product. The following is a list of categories:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="4dd26-113">Ссылка на командлет Skype для бизнеса перемещена в docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="4dd26-113">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="4dd26-114">Перейдя по приведенным ниже ссылкам, вы перейдете на новую страницу docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="4dd26-114">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="4dd26-115">Теперь контент открыт в исходном и доступном для участия в сообществах с помощью GitHub.</span><span class="sxs-lookup"><span data-stu-id="4dd26-115">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="4dd26-116">Интересуетесь участниками?</span><span class="sxs-lookup"><span data-stu-id="4dd26-116">Interested in contributing?</span></span> <span data-ttu-id="4dd26-117">Ознакомьтесь со статьей README в репозитории здесь:<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="4dd26-117">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4dd26-118">Содержание</span><span class="sxs-lookup"><span data-stu-id="4dd26-118">In This Section</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4dd26-119"><a href="lync-server-2013-user-management-cmdlets.md">Командлеты управления пользователями в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4dd26-119"><a href="lync-server-2013-user-management-cmdlets.md">User management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4dd26-120"><a href="lync-server-2013-voice-application-cmdlets.md">Командлеты голосовых приложений в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4dd26-120"><a href="lync-server-2013-voice-application-cmdlets.md">Voice application cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dd26-121"><a href="lync-server-2013-client-management-cmdlets.md">Командлеты управления клиентами в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4dd26-121"><a href="lync-server-2013-client-management-cmdlets.md">Client management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4dd26-122"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Дополнительные командлеты корпоративной голосовой связи в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4dd26-122"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Advanced Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dd26-123"><a href="lync-server-2013-im-and-presence-cmdlets.md">Командлеты для обмена мгновенными сообщениями и присутствия в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4dd26-123"><a href="lync-server-2013-im-and-presence-cmdlets.md">IM and presence cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4dd26-124"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">Командлеты подключения PSTN в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4dd26-124"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">PSTN connectivity cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dd26-125"><a href="lync-server-2013-conferencing-cmdlets.md">Командлеты конференц-связи в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4dd26-125"><a href="lync-server-2013-conferencing-cmdlets.md">Conferencing cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4dd26-126"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Командлеты для телефонов и устройств в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4dd26-126"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Phones and devices cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dd26-127"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Командлеты инфраструктуры и развертывания в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4dd26-127"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Infrastructure and deployment cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4dd26-128"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Командлеты миграции и сосуществования в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4dd26-128"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Migration and coexistence cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dd26-129"><a href="lync-server-2013-security-cmdlets.md">Командлеты безопасности в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4dd26-129"><a href="lync-server-2013-security-cmdlets.md">Security cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4dd26-130"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Командлеты настройки оболочки управления Lync Server в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4dd26-130"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync Server Management Shell configuration cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dd26-131"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Командлеты служб и ролей сервера в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4dd26-131"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Server roles and services cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4dd26-132"><a href="lync-server-2013-mobility-cmdlets.md">Командлеты мобильной связи в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4dd26-132"><a href="lync-server-2013-mobility-cmdlets.md">Mobility cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dd26-133"><a href="lync-server-2013-application-management-cmdlets.md">Командлеты управления приложениями в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4dd26-133"><a href="lync-server-2013-application-management-cmdlets.md">Application management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4dd26-134"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Командлеты сервера сохраняемого чата в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4dd26-134"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Persistent Chat Server cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dd26-135"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Командлеты Федерации и внешнего доступа в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4dd26-135"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Federation and external access cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4dd26-136"><a href="lync-server-2013-centralized-logging-cmdlets.md">Командлеты централизованного ведения журналов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4dd26-136"><a href="lync-server-2013-centralized-logging-cmdlets.md">Centralized Logging cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dd26-137"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Командлеты корпоративной голосовой связи в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4dd26-137"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4dd26-138">См. также</span><span class="sxs-lookup"><span data-stu-id="4dd26-138">See Also</span></span>


[<span data-ttu-id="4dd26-139">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="4dd26-139">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

