---
title: Просмотр сведений о конфигурации магистрали в Скайп для Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Параметров конфигурации магистрали SIP определите связь и возможности между сервером-посредником и шлюза телефонной сети (общего пользования PSTN), общедоступный IP-адрес учреждения (УАТС) или пограничный контроллер сеансов (SBC) у поставщика услуг.
ms.openlocfilehash: 6ba97fa4650b8d62be625256ff4d3b9a3bb7cc68
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32195495"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="a6f79-103">Просмотр сведений о конфигурации магистрали в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="a6f79-103">View trunk configuration information in Skype for Business Server</span></span>

<span data-ttu-id="a6f79-104">Параметров конфигурации магистрали SIP определите связь и возможности между сервером-посредником и шлюза телефонной сети (общего пользования PSTN), общедоступный IP-адрес учреждения (УАТС) или пограничный контроллер сеансов (SBC) у поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="a6f79-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span>

- <span data-ttu-id="a6f79-105">следует включать ли обход сервера-посредника на магистралях;</span><span class="sxs-lookup"><span data-stu-id="a6f79-105">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="a6f79-106">Условия, при которых отправляются пакеты протокола RTCP управления транспорта реального времени.</span><span class="sxs-lookup"><span data-stu-id="a6f79-106">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="a6f79-107">На каждой линии связи требуется ли шифрование по протоколу (SRTP).</span><span class="sxs-lookup"><span data-stu-id="a6f79-107">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="a6f79-108">При установке Скайп для Business Server глобальной коллекции параметров конфигурации магистрали SIP будет создан автоматически.</span><span class="sxs-lookup"><span data-stu-id="a6f79-108">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="a6f79-109">Кроме того, администраторы могут создавать пользовательские коллекции настроек на уровне сайта или службы (только для службы шлюза ТСОП).</span><span class="sxs-lookup"><span data-stu-id="a6f79-109">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="a6f79-110">**Просмотр сведений о конфигурации магистрали SIP с помощью Скайп для панели управления Business Server**</span><span class="sxs-lookup"><span data-stu-id="a6f79-110">**To view SIP trunk configuration information by using Skype for Business Server Control Panel**</span></span>

1. <span data-ttu-id="a6f79-111">В Скайп для панели управления Business Server щелкните **Маршрутизация голосовой связи**и затем щелкните **Настройка линии связи**.</span><span class="sxs-lookup"><span data-stu-id="a6f79-111">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="a6f79-112">На вкладке **Конфигурация магистрали** будет отображен список всех вашей коллекций параметров конфигурации магистрали; для каждого семейства сайтов вы увидите значения для свойства **Name**, **области действия**, **состояние**и **сервера-посредника** и числа **случаев использования PSTN**, **вызов правил номеров**и **именем правил номеров** связанный в коллекции.</span><span class="sxs-lookup"><span data-stu-id="a6f79-112">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collections; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="a6f79-113">Чтобы просмотреть дополнительные сведения о коллекции параметров конфигурации магистральной линии связи, выберите коллекцию интересов, нажмите кнопку **Изменить**и нажмите кнопку **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="a6f79-113">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="a6f79-114">Обратите внимание на то, что можно просматривать подробные сведения только для одной коллекции параметров конфигурации магистрали за раз.</span><span class="sxs-lookup"><span data-stu-id="a6f79-114">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a6f79-115">Просмотр сведений о конфигурации магистрали SIP с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6f79-115">Viewing SIP trunk configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="a6f79-116">SIP-конфигурация магистрали, параметры можно просматривать с помощью Скайп for Business Server PowerShell и командлета Get-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="a6f79-116">SIP trunk configuration settings can be viewed by using Skype for Business Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="a6f79-117">Этот командлет можно выполнять с Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6f79-117">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="a6f79-118">Дополнительные сведения об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server содержатся статьи блога Lync Server Windows PowerShell «Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell» в http://go.microsoft.com/fwlink/p/?linkId=255876.</span><span class="sxs-lookup"><span data-stu-id="a6f79-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at http://go.microsoft.com/fwlink/p/?linkId=255876.</span></span> <span data-ttu-id="a6f79-119">ЗАМЕНА ИЛИ УДАЛЕНИЕ ЭТОЙ ССЫЛКИ.</span><span class="sxs-lookup"><span data-stu-id="a6f79-119">REPLACE OR REMOVE THIS LINK.</span></span>


<span data-ttu-id="a6f79-120">**Для просмотра сведений о конфигурации магистрали SIP**</span><span class="sxs-lookup"><span data-stu-id="a6f79-120">**To view SIP trunk configuration information**</span></span>

<span data-ttu-id="a6f79-121">Чтобы просмотреть сведения о все параметры конфигурации магистрали SIP, введите следующую команду в Скайп для консоли Business Server и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="a6f79-121">To view information about all your SIP trunk configuration settings, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

`Get-CsTrunkConfiguration`

<span data-ttu-id="a6f79-122">Команда возвращает примерно следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="a6f79-122">That will return information similar to this:</span></span>

```
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
<span data-ttu-id="a6f79-123">Для получения дополнительных сведений см раздел справки для командлета [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="a6f79-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>



