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
ms.openlocfilehash: 03b2ea63df8135edfdb3d63d9010aaace9266fd1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102995"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="4c1a3-103">Просмотр сведений о конфигурации магистрали в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4c1a3-103">View trunk configuration information in Skype for Business Server</span></span>

<span data-ttu-id="4c1a3-104">Параметры конфигурации магистрали SIP определяют возможности и отношения между сервером-посредником и шлюзом PSTN, IP-PBX и пограничным контроллером сеансов у поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="4c1a3-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span>

- <span data-ttu-id="4c1a3-105">Следует ли включать обход сервера-посредника на магистралях.</span><span class="sxs-lookup"><span data-stu-id="4c1a3-105">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="4c1a3-106">Условия, при которых передаются пакеты по протоколу RTCP.</span><span class="sxs-lookup"><span data-stu-id="4c1a3-106">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="4c1a3-107">Требуется ли шифрование по протоколу SRTP на каждой магистрали.</span><span class="sxs-lookup"><span data-stu-id="4c1a3-107">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="4c1a3-108">При установке Skype для бизнеса Server создается глобальная коллекция параметров конфигурации магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="4c1a3-108">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="4c1a3-109">Кроме того, администраторы могут создать настраиваемые коллекции параметров в области узла или службы (только для службы шлюза ТСОП).</span><span class="sxs-lookup"><span data-stu-id="4c1a3-109">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="4c1a3-110">**Просмотр сведений о конфигурации магистрали SIP с помощью панели управления Skype для бизнес-серверов**</span><span class="sxs-lookup"><span data-stu-id="4c1a3-110">**To view SIP trunk configuration information by using Skype for Business Server Control Panel**</span></span>

1. <span data-ttu-id="4c1a3-111">В панели управления Skype для бизнес-серверов щелкните **голосовую** маршрутику и нажмите кнопку **Конфигурация магистрали.**</span><span class="sxs-lookup"><span data-stu-id="4c1a3-111">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="4c1a3-112">На **вкладке Конфигурация** магистрали вы увидите список всех коллекций параметров конфигурации магистрали; Для каждой коллекции будут видеться значения свойств обхода  **имен,** **области,** состояния и медиа, а также количество использования  **PSTN,** правил номеров звонков и правил вызываемого номера, связанных с коллекцией.</span><span class="sxs-lookup"><span data-stu-id="4c1a3-112">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collections; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="4c1a3-113">Чтобы узнать дополнительные сведения о коллекции параметров конфигурации магистрали, щелкните интересуемую коллекцию, нажмите кнопку **Изменить** и нажмите **кнопку Показать сведения.**</span><span class="sxs-lookup"><span data-stu-id="4c1a3-113">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="4c1a3-114">Обратите внимание, что подробные сведения можно просматривать только для одной коллекции параметров конфигурации магистрали одновременно.</span><span class="sxs-lookup"><span data-stu-id="4c1a3-114">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4c1a3-115">Просмотр сведений о конфигурации магистрали SIP с помощью Windows PowerShell-кодов</span><span class="sxs-lookup"><span data-stu-id="4c1a3-115">Viewing SIP trunk configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="4c1a3-116">Параметры конфигурации магистрали SIP можно просмотреть с помощью Skype для бизнес-сервера PowerShell и Get-CsTrunkConfiguration-</span><span class="sxs-lookup"><span data-stu-id="4c1a3-116">SIP trunk configuration settings can be viewed by using Skype for Business Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="4c1a3-117">Этот комлет можно выполнить либо из оболочки управления skype для бизнес-серверов, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c1a3-117">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="4c1a3-118">Подробные сведения об использовании удаленных Windows PowerShell для подключения к Skype для бизнеса Server см. в статье блога Lync Server Windows PowerShell "Быстрый запуск: управление Microsoft Lync Server 2010 с использованием удаленной powerShell" на сайте https://go.microsoft.com/fwlink/p/?linkId=255876 .</span><span class="sxs-lookup"><span data-stu-id="4c1a3-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at https://go.microsoft.com/fwlink/p/?linkId=255876.</span></span> <span data-ttu-id="4c1a3-119">ЗАМЕНИТЕ ИЛИ УДАЛИТЕ ЭТУ ССЫЛКУ.</span><span class="sxs-lookup"><span data-stu-id="4c1a3-119">REPLACE OR REMOVE THIS LINK.</span></span>


<span data-ttu-id="4c1a3-120">**Просмотр сведений о конфигурации магистрали SIP**</span><span class="sxs-lookup"><span data-stu-id="4c1a3-120">**To view SIP trunk configuration information**</span></span>

<span data-ttu-id="4c1a3-121">Чтобы просмотреть сведения обо всех параметрах конфигурации магистрали SIP, введите следующую команду в командной оболочке Skype для бизнес-серверов и нажмите кнопку ENTER:</span><span class="sxs-lookup"><span data-stu-id="4c1a3-121">To view information about all your SIP trunk configuration settings, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

```powershell
Get-CsTrunkConfiguration
```

<span data-ttu-id="4c1a3-122">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="4c1a3-122">That will return information similar to this:</span></span>

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
<span data-ttu-id="4c1a3-123">Дополнительные сведения см. в разделе Справка для [cmdlet Get-CsTrunkConfiguration.](/powershell/module/skype/Get-CsTrunkConfiguration)</span><span class="sxs-lookup"><span data-stu-id="4c1a3-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>