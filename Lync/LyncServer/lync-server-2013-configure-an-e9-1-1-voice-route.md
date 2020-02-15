---
title: 'Lync Server 2013: Настройка маршрута голосовой связи E9 – 1 – 1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an E9-1-1 voice route
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398496(v=OCS.15)
ms:contentKeyID: 48184384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e04153e5f5a4b684ac2343d2ef01bfa2c7fd3a9a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-e9-1-1-voice-route-in-lync-server-2013"></a><span data-ttu-id="474e7-102">Настройка маршрута голосовой связи E9 – 1 – 1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474e7-102">Configure an E9-1-1 voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="474e7-103">_**Последнее изменение темы:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="474e7-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="474e7-104">Чтобы развернуть E9-1-1, сначала необходимо настроить маршрут голосовой связи для выполнения экстренных вызовов.</span><span class="sxs-lookup"><span data-stu-id="474e7-104">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="474e7-105">Более подробную информацию о создании маршрутов голосовой связи можно узнать [в статье Создание маршрута голосовых вызовов в Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="474e7-105">For details about creating voice routes, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span> <span data-ttu-id="474e7-106">Можно определить более одного маршрута, если, например, развертывание включает основной магистральный канал SIP и дополнительный магистральный канал SIP.</span><span class="sxs-lookup"><span data-stu-id="474e7-106">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="474e7-107">Чтобы включить информацию о местоположении в приглашение E9-1-1 INVITE, необходимо настроить магистральный канал SIP, который служит для подключения к поставщику службы E9-1-1 для маршрутизации экстренных вызовов через шлюз.</span><span class="sxs-lookup"><span data-stu-id="474e7-107">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="474e7-108">Для этого установите для флага EnablePIDFLOSupport в командлете <STRONG>Set-CsTrunkConfiguration</STRONG> значение True.</span><span class="sxs-lookup"><span data-stu-id="474e7-108">To do this, set the EnablePIDFLOSupport flag on the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to True.</span></span> <span data-ttu-id="474e7-109">Значение по умолчанию для EnablePIDFLOSupport — False.</span><span class="sxs-lookup"><span data-stu-id="474e7-109">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="474e7-110">Например:<CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE></span><span class="sxs-lookup"><span data-stu-id="474e7-110">For example: <CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE></span></span><BR><span data-ttu-id="474e7-111">Не требуется включать получение местоположений для резервных шлюзов ТСОП и шлюзов ELIN.</span><span class="sxs-lookup"><span data-stu-id="474e7-111">It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>



</div>

<span data-ttu-id="474e7-112">Для получения подробных сведений о работе с маршрутами голосовой связи обратитесь к документации по командной консоли Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="474e7-112">For details about working with voice routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="474e7-113">**Set — Кспстнусаже**</span><span class="sxs-lookup"><span data-stu-id="474e7-113">**Set-CsPstnUsage**</span></span>

  - <span data-ttu-id="474e7-114">**Get — Кспстнусаже**</span><span class="sxs-lookup"><span data-stu-id="474e7-114">**Get-CsPstnUsage**</span></span>

  - <span data-ttu-id="474e7-115">**New — Ксвоицерауте**</span><span class="sxs-lookup"><span data-stu-id="474e7-115">**New-CsVoiceRoute**</span></span>

  - <span data-ttu-id="474e7-116">**Get — Ксвоицерауте**</span><span class="sxs-lookup"><span data-stu-id="474e7-116">**Get-CsVoiceRoute**</span></span>

  - <span data-ttu-id="474e7-117">**Set — Ксвоицерауте**</span><span class="sxs-lookup"><span data-stu-id="474e7-117">**Set-CsVoiceRoute**</span></span>

  - <span data-ttu-id="474e7-118">**Remove — Ксвоицерауте**</span><span class="sxs-lookup"><span data-stu-id="474e7-118">**Remove-CsVoiceRoute**</span></span>

<div>

## <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="474e7-119">Настройка маршрута голосовой связи E9-1-1</span><span class="sxs-lookup"><span data-stu-id="474e7-119">To configure an E9-1-1 voice route</span></span>

1.  <span data-ttu-id="474e7-120">Выполните вход в систему компьютера с использованием учетной записи, которая является членом группы RTCUniversalServerAdmins или членом роли администратора CsVoiceAdministrator.</span><span class="sxs-lookup"><span data-stu-id="474e7-120">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>

2.  <span data-ttu-id="474e7-121">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="474e7-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="474e7-122">Выполните следующий командлет, чтобы создать новую запись об использовании ТСОП.</span><span class="sxs-lookup"><span data-stu-id="474e7-122">Run the following cmdlet to create a new PSTN usage record.</span></span>
    
    <span data-ttu-id="474e7-123">Это должно быть то же самое имя, которое будет использоваться для параметра **ТСОП** в политике определения местоположения.</span><span class="sxs-lookup"><span data-stu-id="474e7-123">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="474e7-124">Хотя развертывание будет включать несколько записей об использовании телефона, в следующем примере показано, как добавить «Использование экстренных вызовов» в текущий список доступных использований ТСОП.</span><span class="sxs-lookup"><span data-stu-id="474e7-124">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="474e7-125">Подробнее: [Настройка политик голосовой связи и записей использования PSTN для авторизации функций звонков и привилегий в Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span><span class="sxs-lookup"><span data-stu-id="474e7-125">For details, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  <span data-ttu-id="474e7-126">Выполните следующий командлет, чтобы создать новый маршрут голосовой связи с помощью записи об использовании ТСОП, созданной на предыдущем этапе.</span><span class="sxs-lookup"><span data-stu-id="474e7-126">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="474e7-127">Шаблон номера должен соответствовать шаблону номера, который используется в параметре **Строка набора номера для экстренной связи** политики определения местоположения.</span><span class="sxs-lookup"><span data-stu-id="474e7-127">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="474e7-128">Знак "+" необходим, так как Lync добавляет "+" в экстренные вызовы.</span><span class="sxs-lookup"><span data-stu-id="474e7-128">A "+" sign is needed because Lync adds "+" to emergency calls.</span></span> <span data-ttu-id="474e7-129">«Co1-pstngateway-1» — это идентификатор службы магистрального канала SIP для поставщика службы E9-1-1 или для идентификатора службы шлюза ELIN.</span><span class="sxs-lookup"><span data-stu-id="474e7-129">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="474e7-130">В следующем примере в качестве имени маршрута голосовой связи используется EmergencyRoute.</span><span class="sxs-lookup"><span data-stu-id="474e7-130">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  <span data-ttu-id="474e7-p105">Для магистральных соединений SIP мы также рекомендуем (по желанию) выполнить следующий командлет, чтобы создать локальный маршрут для вызовов, которые не обрабатываются магистральным каналом поставщика службы E9-1-1. Этот маршрут будет использоваться, если подключение к поставщику службы E9-1-1 недоступно.</span><span class="sxs-lookup"><span data-stu-id="474e7-p105">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider’s SIP trunk. This route will be used if the connection to the E9-1-1 service provider is not available.</span></span>
    
    <span data-ttu-id="474e7-133">В следующем примере предполагается, что в политику голосовой связи пользователя включено использование "Локально".</span><span class="sxs-lookup"><span data-stu-id="474e7-133">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

</div>

</div>

<span> </span>

</div>

</div>

</div>

