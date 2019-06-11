---
title: 'Lync Server 2013: удаление существующих параметров конфигурации веб-службы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete existing Web Service configuration settings
ms:assetid: c2b96f4c-4b07-48e6-9ca6-55bc0e0cf5a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182582(v=OCS.15)
ms:contentKeyID: 48185333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faecc3675e4ed22e6bab3a85825ae65c50a8511f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-existing-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="c1c5b-102">Удаление существующих параметров конфигурации веб-службы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1c5b-102">Delete existing Web Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1c5b-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c1c5b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c1c5b-104">Чтобы удалить параметры конфигурации веб-службы, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="c1c5b-104">Follow these steps to delete web service configuration settings.</span></span>

<div>

## <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="c1c5b-105">Удаление параметров конфигурации существующей веб-службы</span><span class="sxs-lookup"><span data-stu-id="c1c5b-105">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="c1c5b-106">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, выполните вход на любой компьютер в сети, в которой вы развернули Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c1c5b-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="c1c5b-107">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c1c5b-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c1c5b-108">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c1c5b-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c1c5b-109">В левой панели навигации щелкните **Безопасность**, а затем щелкните **Веб-служба**.</span><span class="sxs-lookup"><span data-stu-id="c1c5b-109">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="c1c5b-110">На странице **Веб-служба** в поле поиска введите полностью или частично имя политики, которую требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="c1c5b-110">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="c1c5b-111">В списке политик выберите необходимую политику, щелкните **Правка**, затем выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="c1c5b-111">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="c1c5b-112">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c1c5b-112">Click **OK**.</span></span>

</div>

<div>

## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c1c5b-113">Удаление параметров конфигурации веб-службы с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1c5b-113">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c1c5b-114">Вы можете удалить параметры конфигурации веб-службы с помощью Windows PowerShell и командлета **Remove-ксвебсервицеконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="c1c5b-114">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="c1c5b-115">Этот командлет можно выполнить из управляющей оболочки Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1c5b-115">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c1c5b-116">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1c5b-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="c1c5b-117">Удаление конкретной коллекции параметров конфигурации веб-служб</span><span class="sxs-lookup"><span data-stu-id="c1c5b-117">To delete a specific collection of web service configuration settings</span></span>

  - <span data-ttu-id="c1c5b-118">Следующая команда удаляет параметры безопасности веб-служб, относящиеся к сайту Redmond:</span><span class="sxs-lookup"><span data-stu-id="c1c5b-118">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
        Remove-CsWebServiceConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="c1c5b-119">Удаление всех параметров конфигурации веб-служб, относящихся к области сайта</span><span class="sxs-lookup"><span data-stu-id="c1c5b-119">To delete all of the web service configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="c1c5b-120">Следующая команда удаляет все параметры безопасности веб-служб, относящиеся к области службы:</span><span class="sxs-lookup"><span data-stu-id="c1c5b-120">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
        Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="c1c5b-121">Удаление всех параметров конфигурации веб-служб, позволяющих проверку подлинности с помощью сертификатов</span><span class="sxs-lookup"><span data-stu-id="c1c5b-121">To delete all of the web service configuration settings that allow certificate authentication</span></span>

  - <span data-ttu-id="c1c5b-122">Следующая команда удаляет все параметры безопасности веб-служб, позволяющие использовать проверку подлинности с помощью сертификатов:</span><span class="sxs-lookup"><span data-stu-id="c1c5b-122">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
        Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration

</div>

<span data-ttu-id="c1c5b-123">Подробности можно найти в разделе [Remove-ксвебсервицеконфигуратион](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration).</span><span class="sxs-lookup"><span data-stu-id="c1c5b-123">For details, see [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c1c5b-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c1c5b-124">See Also</span></span>


[<span data-ttu-id="c1c5b-125">Настройка проверки подлинности на панели управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1c5b-125">Configuring authentication in the Lync Server 2013 Control Panel</span></span>](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

