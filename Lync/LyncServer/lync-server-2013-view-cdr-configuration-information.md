---
title: 'Lync Server 2013: Просмотр сведений о конфигурации CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View CDR configuration information
ms:assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688096(v=OCS.15)
ms:contentKeyID: 49733695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccf5658b49118f4053f0bd76b18273fb77f90237
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136857"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-cdr-configuration-information-in-lync-server-2013"></a><span data-ttu-id="cb172-102">Просмотр сведений о конфигурации CDR в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb172-102">View CDR configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb172-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="cb172-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="cb172-p101">Служба регистрации вызовов (CDR) позволяет отслеживать использование таких услуг, как сеансы обмена одноранговыми мгновенными сообщениями, телефонные вызовы с передачей речи по IP-сетям (VoIP) и вызовы конференц-связи. Данные о таком использовании телефонии включают сведения о том, кто кому звонил, когда звонили и каким долгим был телефонный разговор.</span><span class="sxs-lookup"><span data-stu-id="cb172-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="cb172-106">При установке Microsoft Lync Server 2013 создается одна глобальная коллекция параметров конфигурации CDR.</span><span class="sxs-lookup"><span data-stu-id="cb172-106">When you install Microsoft Lync Server 2013, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="cb172-107">Администраторы могут создавать пользовательские коллекции параметров, которые могут применяться к отдельным сайтам.</span><span class="sxs-lookup"><span data-stu-id="cb172-107">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="cb172-108">Параметры конфигурации CDR, используемые в Организации, можно просмотреть с помощью панели управления Lync Server или командлета [Get – CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="cb172-108">You can view the CDR configuration settings in use in your organization by using Lync Server Control Panel or the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet.</span></span>

<div>

## <a name="to-view-cdr-configuration-information-by-using-lync-server-control-panel"></a><span data-ttu-id="cb172-109">Просмотр сведений о конфигурации CDR с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="cb172-109">To view CDR configuration information by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="cb172-110">В панели управления Lync Server щелкните **мониторинг и архивация**.</span><span class="sxs-lookup"><span data-stu-id="cb172-110">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="cb172-p103">Список всех параметров конфигурации CDR отображается на вкладке **Регистрация вызовов**. Для каждой коллекции параметров вы увидите **Имя**, была ли включена регистрация вызовов или нет (свойство **CDR**) независимо от включения очистки (свойство **Очистка CDR**). Для просмотра подробных сведений о коллекции дважды щелкните ее или выберите нужную коллекцию, нажмите кнопку **Правка** и щелкните **Показать подробности**. Учтите, что вы можете просматривать подробную информацию только для одной коллекции параметров конфигурации CDR за один раз.</span><span class="sxs-lookup"><span data-stu-id="cb172-p103">A list of all your CDR configuration settings will be displayed in the **Call Detail Recording** tab; for each collection of settings you will see the collection **Name**; whether or not CDR has been enabled (the **CDR** property); and whether or not purging has been enabled (the **CDR purging** property). To see detailed information about a collection, double-click the collection, or select the appropriate collection, click **Edit**, and then click **Show Details**. Note that you can only view detailed information for a single collection of CDR configuration settings at a time.</span></span>

</div>

<div>

## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="cb172-114">Просмотр сведений о конфигурации CDR с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cb172-114">Viewing CDR Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="cb172-115">Параметры конфигурации CDR можно просмотреть с помощью Windows PowerShell и командлета Get – CsCdrConfiguration.</span><span class="sxs-lookup"><span data-stu-id="cb172-115">You can view CDR configuration settings by using Windows PowerShell and the Get-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="cb172-116">Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb172-116">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="cb172-117">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="cb172-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-cdr-configuration-information"></a><span data-ttu-id="cb172-118">Просмотр данных конфигурации CDR</span><span class="sxs-lookup"><span data-stu-id="cb172-118">To view CDR configuration information</span></span>

  - <span data-ttu-id="cb172-119">Чтобы просмотреть сведения обо всех параметрах конфигурации CDR, введите следующую команду в командной консоли Lync Server, а затем нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="cb172-119">To view information about all your CDR configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsCdrConfiguration
    
    <span data-ttu-id="cb172-120">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="cb172-120">That will return information similar to this:</span></span>
    
        Identity               : Global
        EnableCDR              : True
        EnablePurging          : True
        KeepCallDetailForDays  : 90
        KeepErrorReportForDays : 60
        PurgeHourOfDay         : 2

</div>

<span data-ttu-id="cb172-121">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Get – CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="cb172-121">For more information, see the help topic for the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

