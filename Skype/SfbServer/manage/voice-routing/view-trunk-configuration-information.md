---
title: Просмотр сведений о конфигурации магистрали в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Параметры конфигурации магистрали SIP определяют возможности и отношения между сервером-посредником и шлюзом PSTN, IP-PBX и пограничным контроллером сеансов у поставщика услуг.
ms.openlocfilehash: c473c3fc19138ac91b44dff8552555418d36533f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826169"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="970c0-103">Просмотр сведений о конфигурации магистрали в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="970c0-103">View trunk configuration information in Skype for Business Server</span></span>

<span data-ttu-id="970c0-104">Параметры конфигурации магистрали SIP определяют возможности и отношения между сервером-посредником и шлюзом PSTN, IP-PBX и пограничным контроллером сеансов у поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="970c0-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span>

- <span data-ttu-id="970c0-105">Следует ли включать обход сервера-посредника на магистралях.</span><span class="sxs-lookup"><span data-stu-id="970c0-105">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="970c0-106">Условия, при которых передаются пакеты по протоколу RTCP.</span><span class="sxs-lookup"><span data-stu-id="970c0-106">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="970c0-107">Требуется ли шифрование по протоколу SRTP на каждой магистрали.</span><span class="sxs-lookup"><span data-stu-id="970c0-107">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="970c0-108">При установке Skype для бизнеса Server создается глобальная коллекция параметров конфигурации магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="970c0-108">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="970c0-109">Кроме того, администраторы могут создать настраиваемые коллекции параметров в области узла или службы (только для службы шлюза ТСОП).</span><span class="sxs-lookup"><span data-stu-id="970c0-109">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="970c0-110">**Просмотр сведений о конфигурации магистрали SIP с помощью панели управления Skype для бизнеса Server**</span><span class="sxs-lookup"><span data-stu-id="970c0-110">**To view SIP trunk configuration information by using Skype for Business Server Control Panel**</span></span>

1. <span data-ttu-id="970c0-111">В панели управления Skype для бизнеса Server щелкните "Маршрутация голосовой почты" **и** выберите **"Конфигурация магистрали".**</span><span class="sxs-lookup"><span data-stu-id="970c0-111">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="970c0-112">На **вкладке "Конфигурация** магистрали" вы увидите список всех коллекций параметров конфигурации магистрали; для каждой коллекции вы увидите значения свойств **Name,** **Scope,** **State** и **Media Bypass,** а также количество вариантов  использования **PSTN,** правил номеров звонков и правил вызываемого номера, связанных с коллекцией.</span><span class="sxs-lookup"><span data-stu-id="970c0-112">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collections; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="970c0-113">Чтобы увидеть дополнительные сведения о коллекции параметров конфигурации магистрали, щелкните коллекцию параметров, нажмите кнопку "Изменить" **и** выберите **"Показать подробности".**</span><span class="sxs-lookup"><span data-stu-id="970c0-113">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="970c0-114">Обратите внимание, что вы можете просматривать подробные сведения только для одной коллекции параметров конфигурации магистрали одновременно.</span><span class="sxs-lookup"><span data-stu-id="970c0-114">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="970c0-115">Просмотр сведений о конфигурации магистрали SIP с помощью Windows PowerShell управления</span><span class="sxs-lookup"><span data-stu-id="970c0-115">Viewing SIP trunk configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="970c0-116">Параметры конфигурации магистрали SIP можно просмотреть с помощью Skype для бизнеса Server PowerShell и Get-CsTrunkConfiguration управления.</span><span class="sxs-lookup"><span data-stu-id="970c0-116">SIP trunk configuration settings can be viewed by using Skype for Business Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="970c0-117">Этот cmdlet можно запустить либо из оболочки управления Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="970c0-117">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="970c0-118">Подробные сведения об использовании удаленного Windows PowerShell для подключения к Skype для бизнеса Server см. в статье блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 с помощью удаленной powerShell" по этой https://go.microsoft.com/fwlink/p/?linkId=255876 статье.</span><span class="sxs-lookup"><span data-stu-id="970c0-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at https://go.microsoft.com/fwlink/p/?linkId=255876.</span></span> <span data-ttu-id="970c0-119">ЗАМЕНИТЕ ИЛИ УДАЛИТЕ ЭТУ ССЫЛКУ.</span><span class="sxs-lookup"><span data-stu-id="970c0-119">REPLACE OR REMOVE THIS LINK.</span></span>


<span data-ttu-id="970c0-120">**Просмотр сведений о конфигурации магистрали SIP**</span><span class="sxs-lookup"><span data-stu-id="970c0-120">**To view SIP trunk configuration information**</span></span>

<span data-ttu-id="970c0-121">Чтобы просмотреть сведения обо всех параметрах конфигурации магистрали SIP, введите следующую команду в командной оболочке Skype для бизнеса Server и нажмите ввод:</span><span class="sxs-lookup"><span data-stu-id="970c0-121">To view information about all your SIP trunk configuration settings, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

```powershell
Get-CsTrunkConfiguration
```

<span data-ttu-id="970c0-122">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="970c0-122">That will return information similar to this:</span></span>

```console
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
```
<span data-ttu-id="970c0-123">Дополнительные сведения см. в разделе справки по [cmdlet Get-CsTrunkConfiguration.](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)</span><span class="sxs-lookup"><span data-stu-id="970c0-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>



