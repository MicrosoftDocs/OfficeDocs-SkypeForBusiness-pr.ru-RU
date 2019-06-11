---
title: Удаление существующей коллекции параметров конфигурации клиентской версии
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of client version configuration settings
ms:assetid: 70bf1216-d0d2-45ce-881f-b8edadf3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898480(v=OCS.15)
ms:contentKeyID: 50873760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a71df7af1f0a6158cb61e780b44ed4227d32018
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="eecf6-102">Удаление существующей коллекции параметров конфигурации клиентской версии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eecf6-102">Delete an existing collection of client version configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eecf6-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="eecf6-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="eecf6-104">Если вы хотите удалить параметры конфигурации клиента, уже настроенные для сайта, вы можете удалить параметры из панели управления Lync Server 2013 или оболочки управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eecf6-104">If you want to remove the client configuration settings that have been previously configured for a site, you can remove the settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-remove-client-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="eecf6-105">Удаление параметров конфигурации клиента с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="eecf6-105">To remove client configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="eecf6-106">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="eecf6-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="eecf6-107">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eecf6-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="eecf6-108">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="eecf6-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="eecf6-109">На панели навигации слева выберите пункт **Клиенты**, а затем нажмите кнопку Навигация по **конфигурации версии клиента** .</span><span class="sxs-lookup"><span data-stu-id="eecf6-109">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="eecf6-110">Выберите сайт, нажмите кнопку **изменить**, а затем — **Удалить**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="eecf6-110">Select the site, click **Edit**, click **Delete**, and then click **OK**.</span></span>

</div>

<div>

## <a name="removing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="eecf6-111">Удаление параметров конфигурации клиентской версии с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eecf6-111">Removing Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="eecf6-112">Вы можете удалить параметры конфигурации версии клиента с помощью командлета **Remove-ксклиентверсионконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="eecf6-112">You can delete client version configuration settings by using the **Remove-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="eecf6-113">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eecf6-113">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="eecf6-114">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eecf6-114">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-client-version-configuration-settings"></a><span data-ttu-id="eecf6-115">Удаление заданной коллекции параметров конфигурации клиентской версии</span><span class="sxs-lookup"><span data-stu-id="eecf6-115">To remove a specified collection of client version configuration settings</span></span>

  - <span data-ttu-id="eecf6-116">Следующая команда удаляет параметры конфигурации для версии клиента, примененные к сайту Redmond.</span><span class="sxs-lookup"><span data-stu-id="eecf6-116">The following command removes the client version configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsClientVersionConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="eecf6-117">Удаление всех параметров конфигурации для версии клиента, примененных к области сайта</span><span class="sxs-lookup"><span data-stu-id="eecf6-117">To remove all the client version configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="eecf6-118">Эта команда удаляет все параметры конфигурации клиентской версии, настроенные на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="eecf6-118">This command removes all the client version configuration settings configured at the site scope:</span></span>
    
        Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-based-on-the-value-of-the-defaultaction-property"></a><span data-ttu-id="eecf6-119">Удаление всех параметров конфигурации клиентской версии на основе значения свойства Дефаултактион</span><span class="sxs-lookup"><span data-stu-id="eecf6-119">To remove all the client version configuration settings based on the value of the DefaultAction property</span></span>

  - <span data-ttu-id="eecf6-120">Эта команда удаляет все параметры конфигурации клиентской версии, для которых для действия по умолчанию установлено значение "блокировать".</span><span class="sxs-lookup"><span data-stu-id="eecf6-120">And this command removes all the client version configuration settings where the default action has been set to "Block":</span></span>
    
        Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block" | Remove-CsClientVersionConfiguration

</div>

<span data-ttu-id="eecf6-121">Дополнительные сведения можно найти в разделе справки по командлету [Remove-ксклиентверсионконфигуратион](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="eecf6-121">For details, see the Help topic for the [Remove-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

