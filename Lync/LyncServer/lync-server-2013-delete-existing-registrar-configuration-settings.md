---
title: 'Lync Server 2013: удаление существующих параметров конфигурации регистратора'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Registrar configuration settings
ms:assetid: ae43cd75-cae4-4f78-b037-779a2cdb583b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182571(v=OCS.15)
ms:contentKeyID: 48185132
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19f127efa6e2cab04434dd8de6e541897d50483f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-existing-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="0953e-102">Удаление существующих параметров конфигурации регистратора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0953e-102">Delete existing Registrar configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0953e-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="0953e-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="0953e-104">В этом разделе приведены инструкции по удалению Регистратора.</span><span class="sxs-lookup"><span data-stu-id="0953e-104">Follow these steps to delete a Registrar.</span></span>

<div>

## <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="0953e-105">Удаление параметров конфигурации регистратора</span><span class="sxs-lookup"><span data-stu-id="0953e-105">To delete Registrar configuration settings</span></span>

1.  <span data-ttu-id="0953e-106">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0953e-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="0953e-107">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0953e-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0953e-108">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0953e-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0953e-109">В левой панели навигации щелкните **Security** (Безопасность) и затем щелкните **Registrar** (Регистратор).</span><span class="sxs-lookup"><span data-stu-id="0953e-109">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="0953e-110">На странице **Registrar** (Регистратор) введите имя удаляемого Регистратора или часть имени в поле поиска.</span><span class="sxs-lookup"><span data-stu-id="0953e-110">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>

5.  <span data-ttu-id="0953e-111">Выберите требуемого Регистратора, а затем щелкните **Edit** (Изменить) и **Delete** (Удалить).</span><span class="sxs-lookup"><span data-stu-id="0953e-111">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="0953e-112">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0953e-112">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0953e-113">Удаление параметров конфигурации регистратора с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0953e-113">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0953e-114">Вы можете удалить параметры конфигурации регистратора с помощью Windows PowerShell и командлета **Remove – CsProxyConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="0953e-114">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="0953e-115">Этот командлет можно выполнить из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0953e-115">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0953e-116">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="0953e-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="0953e-117">Удаление определенного набора параметров безопасности Регистратора</span><span class="sxs-lookup"><span data-stu-id="0953e-117">To remove a specific set of Registrar security settings</span></span>

  - <span data-ttu-id="0953e-118">Следующая команда удаляет параметры безопасности Регистратора, применяемые к пограничному серверу atl-edge-011.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="0953e-118">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="0953e-119">Удаление всех параметров безопасности Регистратора, применяемых на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="0953e-119">To remove all of the Registrar security settings applied to the site scope</span></span>

  - <span data-ttu-id="0953e-120">Следующая команда удаляет все параметры безопасности Регистратора, применяемые к службе Регистратора.</span><span class="sxs-lookup"><span data-stu-id="0953e-120">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="0953e-121">Удаление всех параметров безопасности Регистратора, разрешающих проверку подлинности NTLM</span><span class="sxs-lookup"><span data-stu-id="0953e-121">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

  - <span data-ttu-id="0953e-122">Следующая команда удаляет все параметры безопасности Регистратора, разрешающие использование NTLM для проверки подлинности клиентов.</span><span class="sxs-lookup"><span data-stu-id="0953e-122">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

</div>

<span data-ttu-id="0953e-123">Дополнительные сведения см. в разделе [Remove – CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration).</span><span class="sxs-lookup"><span data-stu-id="0953e-123">For details, see [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

