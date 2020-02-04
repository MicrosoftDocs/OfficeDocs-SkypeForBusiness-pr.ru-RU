---
title: 'Lync Server 2013: Просмотр сведений о конфигурации магистрали'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View trunk configuration information
ms:assetid: ebe10e14-08c2-4797-9254-9ed89516d5cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721927(v=OCS.15)
ms:contentKeyID: 49733862
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77f53a4263fd0e0b64ccd6894d27e30c0c5be95c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-trunk-configuration-information-in-lync-server-2013"></a><span data-ttu-id="3ef29-102">Просмотр сведений о магистральной конфигурации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ef29-102">View trunk configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ef29-103">_**Тема последнего изменения:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="3ef29-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="3ef29-104">Параметры конфигурации магистральной магистрали SIP определяют связь и возможности между сервером-посредником и шлюзом коммутируемой телефонной сети (PSTN), Интернет-ПРОТОКОЛом (УАТС) или контроллером границ сеанса (SBC) в поставщике услуг.</span><span class="sxs-lookup"><span data-stu-id="3ef29-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="3ef29-105">Эти параметры, в частности, определяют следующее:</span><span class="sxs-lookup"><span data-stu-id="3ef29-105">These settings do such things as specify:</span></span>

  - <span data-ttu-id="3ef29-106">следует включать ли обход сервера-посредника на магистралях;</span><span class="sxs-lookup"><span data-stu-id="3ef29-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="3ef29-107">Условия, при которых отправляются пакеты протокола управления транспортом в реальном времени (РТКП).</span><span class="sxs-lookup"><span data-stu-id="3ef29-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="3ef29-108">Требуется ли шифрование на всех магистральах в режиме реального времени (SRTP).</span><span class="sxs-lookup"><span data-stu-id="3ef29-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="3ef29-109">При установке Microsoft Lync Server 2013 создается глобальная коллекция параметров конфигурации магистральной магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="3ef29-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="3ef29-110">Кроме того, администраторы могут создавать пользовательские коллекции настроек на уровне сайта или службы (только для службы шлюза ТСОП).</span><span class="sxs-lookup"><span data-stu-id="3ef29-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<div>

## <a name="to-view-sip-trunk-configuration-information-by-using-lync-server-control-panel"></a><span data-ttu-id="3ef29-111">Просмотр сведений о настройке магистральной магистрали SIP с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="3ef29-111">To view SIP trunk configuration information by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3ef29-112">На панели управления Lync Server щелкните **Маршрутизация голосовой связи** и выберите **Конфигурация магистрали**.</span><span class="sxs-lookup"><span data-stu-id="3ef29-112">In Lync Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="3ef29-113">На вкладке **Настройка магистрали** вы увидите список всех параметров конфигурации магистрали. для каждой коллекции вы увидите значения свойств **пропускаемых** **имен**, **областей**, **состояний**и мультимедиа, а также количество **использованных PSTN**, **правил для номерных номеров**и **число правил** , связанных с коллекцией.</span><span class="sxs-lookup"><span data-stu-id="3ef29-113">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collection; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="3ef29-114">Чтобы просмотреть дополнительные сведения о коллекции параметров конфигурации магистрали, щелкните нужную коллекцию, нажмите кнопку **изменить**, а затем выберите команду **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="3ef29-114">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="3ef29-115">Обратите внимание на то, что вы можете просматривать подробные сведения только для одной коллекции параметров конфигурации канала за один раз.</span><span class="sxs-lookup"><span data-stu-id="3ef29-115">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

</div>

<div>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3ef29-116">Просмотр сведений о настройке магистральной магистрали SIP с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ef29-116">Viewing SIP Trunk Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3ef29-117">Параметры конфигурации магистральной магистрали SIP можно просмотреть с помощью Lync Server PowerShell и командлета Get-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="3ef29-117">SIP trunk configuration settings can be viewed by using Lync Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="3ef29-118">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ef29-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="3ef29-119">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ef29-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-sip-trunk-configuration-information"></a><span data-ttu-id="3ef29-120">Просмотр сведений о настройке магистральной магистрали SIP</span><span class="sxs-lookup"><span data-stu-id="3ef29-120">To view SIP trunk configuration information</span></span>

  - <span data-ttu-id="3ef29-121">Чтобы просмотреть сведения о всех параметрах настройки магистральной магистрали SIP, введите в командной консоли Lync Server следующую команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="3ef29-121">To view information about all your SIP trunk configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsTrunkConfiguration
    
    <span data-ttu-id="3ef29-122">Команда возвращает примерно следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="3ef29-122">That will return information similar to this:</span></span>
    
        Identity                                  : Global
        OutboundTranslationRulesList              : {}
        SipResponseCodeTranslationRulesList       : {}
        OutboundCallingNumberTranslationRulesList : {}
        PstnUsages                                : {}
        Description                               :
        ConcentratedTopology                      : True
        EnableBypass                              : False
        EnableMobileTrunkSupport                  : False
        EnableReferSupport                        : True
        EnableSessionTimer                        : False
        EnableSignalBoost                         : False
        MaxEarlyDialogs                           : 20
        RemovePlusFromUri                         : False
        RTCPActiveCalls                           : True
        RTCPCallsOnHold                           : True
        SRTPMode                                  : Required
        EnablePIDFLOSupport                       : False
        EnableRTPLatching                         : False
        EnableOnlineVoice                         : False
        ForwardCallHistory                        : False
        Enable3pccRefer                           : False
        ForwardPAI                                : False
        EnableFastFailoverTimer                   : True

</div>

<span data-ttu-id="3ef29-123">Дополнительные сведения можно найти в разделе справки по командлету [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="3ef29-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

