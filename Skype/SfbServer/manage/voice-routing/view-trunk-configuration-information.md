---
title: Просмотр сведений о настройке магистрали в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Параметры конфигурации магистральной магистрали SIP определяют связь и возможности между сервером-посредником и шлюзом коммутируемой телефонной сети (PSTN), Интернет-ПРОТОКОЛом (УАТС) или контроллером границ сеанса (SBC) в поставщике услуг.
ms.openlocfilehash: 40820729727ec02e5494e69c773d7fbd3d7b1154
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888488"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="5cb03-103">Просмотр сведений о настройке магистрали в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5cb03-103">View trunk configuration information in Skype for Business Server</span></span>

<span data-ttu-id="5cb03-104">Параметры конфигурации магистральной магистрали SIP определяют связь и возможности между сервером-посредником и шлюзом коммутируемой телефонной сети (PSTN), Интернет-ПРОТОКОЛом (УАТС) или контроллером границ сеанса (SBC) в поставщике услуг.</span><span class="sxs-lookup"><span data-stu-id="5cb03-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span>

- <span data-ttu-id="5cb03-105">следует включать ли обход сервера-посредника на магистралях;</span><span class="sxs-lookup"><span data-stu-id="5cb03-105">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="5cb03-106">Условия, при которых отправляются пакеты протокола управления транспортом в реальном времени (РТКП).</span><span class="sxs-lookup"><span data-stu-id="5cb03-106">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="5cb03-107">Требуется ли шифрование на всех магистральах в режиме реального времени (SRTP).</span><span class="sxs-lookup"><span data-stu-id="5cb03-107">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="5cb03-108">При установке Skype для бизнеса Server для вас создается глобальная коллекция параметров конфигурации магистральной магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="5cb03-108">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="5cb03-109">Кроме того, администраторы могут создавать пользовательские коллекции настроек на уровне сайта или службы (только для службы шлюза ТСОП).</span><span class="sxs-lookup"><span data-stu-id="5cb03-109">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="5cb03-110">**Просмотр сведений о настройке магистральной магистрали SIP с помощью панели управления Skype для бизнеса Server**</span><span class="sxs-lookup"><span data-stu-id="5cb03-110">**To view SIP trunk configuration information by using Skype for Business Server Control Panel**</span></span>

1. <span data-ttu-id="5cb03-111">На панели управления Skype для бизнеса Server нажмите кнопку **Маршрутизация голоса**и выберите пункт **Настройка магистрали**.</span><span class="sxs-lookup"><span data-stu-id="5cb03-111">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="5cb03-112">На вкладке **Настройка магистрали** вы увидите список всех коллекций параметров конфигурации канала. для каждой коллекции вы увидите значения свойств **пропускаемых** **имен**, **областей**, **состояний**и мультимедиа, а также количество **использованных PSTN**, **правил для номерных номеров**и **число правил** , связанных с коллекцией.</span><span class="sxs-lookup"><span data-stu-id="5cb03-112">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collections; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="5cb03-113">Чтобы просмотреть дополнительные сведения о коллекции параметров конфигурации магистрали, щелкните нужную коллекцию, нажмите кнопку **изменить**, а затем выберите команду **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="5cb03-113">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="5cb03-114">Обратите внимание на то, что вы можете просматривать подробные сведения только для одной коллекции параметров конфигурации канала за один раз.</span><span class="sxs-lookup"><span data-stu-id="5cb03-114">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5cb03-115">Просмотр сведений о настройке магистральной магистрали SIP с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5cb03-115">Viewing SIP trunk configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="5cb03-116">Параметры конфигурации магистральной магистрали SIP можно просмотреть с помощью Skype для бизнеса Server PowerShell и командлета Get-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="5cb03-116">SIP trunk configuration settings can be viewed by using Skype for Business Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="5cb03-117">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5cb03-117">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="5cb03-118">Дополнительные сведения об использовании удаленной оболочки Windows PowerShell для подключения к серверу Skype для бизнеса можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в https://go.microsoft.com/fwlink/p/?linkId=255876блоге Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5cb03-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at https://go.microsoft.com/fwlink/p/?linkId=255876.</span></span> <span data-ttu-id="5cb03-119">ЗАМЕНА ИЛИ УДАЛЕНИЕ ЭТОЙ ССЫЛКИ.</span><span class="sxs-lookup"><span data-stu-id="5cb03-119">REPLACE OR REMOVE THIS LINK.</span></span>


<span data-ttu-id="5cb03-120">**Просмотр сведений о настройке магистральной магистрали SIP**</span><span class="sxs-lookup"><span data-stu-id="5cb03-120">**To view SIP trunk configuration information**</span></span>

<span data-ttu-id="5cb03-121">Чтобы просмотреть сведения о всех параметрах настройки магистральной магистрали SIP, введите в командной консоли Skype для Business Server указанную ниже команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="5cb03-121">To view information about all your SIP trunk configuration settings, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

```powershell
Get-CsTrunkConfiguration
```

<span data-ttu-id="5cb03-122">Команда возвращает примерно следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="5cb03-122">That will return information similar to this:</span></span>

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
<span data-ttu-id="5cb03-123">Дополнительные сведения можно найти в разделе справки по командлету [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="5cb03-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>



