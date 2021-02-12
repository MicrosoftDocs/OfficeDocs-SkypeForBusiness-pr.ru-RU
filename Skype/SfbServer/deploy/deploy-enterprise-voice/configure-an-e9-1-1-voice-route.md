---
title: Настройка маршрута голосовой почты E9-1-1 в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Настройка маршрутов голосовой почты E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: b5f3d12bb586a65fc1c553a021c1a27efb0c7f77
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804179"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a><span data-ttu-id="462bf-103">Настройка маршрута голосовой почты E9-1-1 в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="462bf-103">Configure an E9-1-1 voice route in Skype for Business Server</span></span>
 
<span data-ttu-id="462bf-104">Настройка маршрутов голосовой почты E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="462bf-104">Configure E9-1-1 voice routes in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="462bf-105">Чтобы развернуть E9-1-1, сначала необходимо настроить маршрут голосовой связи для выполнения экстренных вызовов.</span><span class="sxs-lookup"><span data-stu-id="462bf-105">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="462bf-106">Дополнительные сведения о создании маршрутов голосовых вызовов см. в теме ["Создание или изменение маршрута голосовой почты" в Skype для бизнеса.](create-or-modify-a-voice-route.md)</span><span class="sxs-lookup"><span data-stu-id="462bf-106">For details about creating voice routes, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span> <span data-ttu-id="462bf-107">Можно определить более одного маршрута, если, например, развертывание включает основной магистральный канал SIP и дополнительный магистральный канал SIP.</span><span class="sxs-lookup"><span data-stu-id="462bf-107">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="462bf-108">Чтобы включить информацию о местоположении в приглашение E9-1-1 INVITE, необходимо настроить магистральный канал SIP, который служит для подключения к поставщику службы E9-1-1 для маршрутизации экстренных вызовов через шлюз.</span><span class="sxs-lookup"><span data-stu-id="462bf-108">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="462bf-109">Для этого установите для флага EnablePIDFLOSupport в командлете **Set-CsTrunkConfiguration** значение True.</span><span class="sxs-lookup"><span data-stu-id="462bf-109">To do this, set the EnablePIDFLOSupport flag on the **Set-CsTrunkConfiguration** cmdlet to True.</span></span> <span data-ttu-id="462bf-110">Значение по умолчанию для EnablePIDFLOSupport — False.</span><span class="sxs-lookup"><span data-stu-id="462bf-110">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="462bf-111">Например, нет необходимости в включении приемных расположений для откатных шлюзов телефонной сети общего нахождения (PSTN) и шлюзов `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` ELIN.</span><span class="sxs-lookup"><span data-stu-id="462bf-111">For example: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>
  
### <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="462bf-112">Настройка маршрута голосовой связи E9-1-1</span><span class="sxs-lookup"><span data-stu-id="462bf-112">To configure an E9-1-1 voice route</span></span>

1. <span data-ttu-id="462bf-113">Выполните вход в систему компьютера с использованием учетной записи, которая является членом группы RTCUniversalServerAdmins или членом роли администратора CsVoiceAdministrator.</span><span class="sxs-lookup"><span data-stu-id="462bf-113">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>
    
2.  <span data-ttu-id="462bf-114">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="462bf-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="462bf-115">Выполните следующий командлет, чтобы создать новую запись об использовании ТСОП.</span><span class="sxs-lookup"><span data-stu-id="462bf-115">Run the following cmdlet to create a new PSTN usage record.</span></span> 
    
    <span data-ttu-id="462bf-116">Это должно быть то же самое имя, которое будет использоваться для параметра **ТСОП** в политике определения местоположения.</span><span class="sxs-lookup"><span data-stu-id="462bf-116">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="462bf-117">Хотя развертывание будет включать несколько записей об использовании телефона, в следующем примере показано, как добавить «Использование экстренных вызовов» в текущий список доступных использований ТСОП.</span><span class="sxs-lookup"><span data-stu-id="462bf-117">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="462bf-118">For details, see [Configure voice policies, PSTN usage records, and voice routes in Skype for Business](voice-and-pstn.md).</span><span class="sxs-lookup"><span data-stu-id="462bf-118">For details, see [Configure voice policies, PSTN usage records, and voice routes in Skype for Business](voice-and-pstn.md).</span></span>
    
   ```powershell
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. <span data-ttu-id="462bf-119">Выполните следующий командлет, чтобы создать новый маршрут голосовой связи с помощью записи об использовании ТСОП, созданной на предыдущем этапе.</span><span class="sxs-lookup"><span data-stu-id="462bf-119">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="462bf-120">Шаблон номера должен соответствовать шаблону номера, который используется в параметре **Строка набора номера для экстренной связи** политики определения местоположения.</span><span class="sxs-lookup"><span data-stu-id="462bf-120">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="462bf-121">Знак "+" необходим, так как Skype для бизнеса добавляет "+" в экстренные вызовы.</span><span class="sxs-lookup"><span data-stu-id="462bf-121">A "+" sign is needed because Skype for Business adds "+" to emergency calls.</span></span> <span data-ttu-id="462bf-122">«Co1-pstngateway-1» — это идентификатор службы магистрального канала SIP для поставщика службы E9-1-1 или для идентификатора службы шлюза ELIN.</span><span class="sxs-lookup"><span data-stu-id="462bf-122">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="462bf-123">В следующем примере в качестве имени маршрута голосовой связи используется EmergencyRoute.</span><span class="sxs-lookup"><span data-stu-id="462bf-123">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
   ```powershell
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. <span data-ttu-id="462bf-124">При желании для подключений магистрали SIP рекомендуется выполнить следующий cmdlet, чтобы создать локальный маршрут для вызовов, которые не обрабатываются магистралью SIP поставщика услуг E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="462bf-124">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider's SIP trunk.</span></span> <span data-ttu-id="462bf-125">Этот маршрут будет использоваться, если подключение к поставщику службы E9-1-1 недоступно.</span><span class="sxs-lookup"><span data-stu-id="462bf-125">This route will be used if the connection to the E9-1-1 service provider is not available.</span></span> 
    
    <span data-ttu-id="462bf-126">В следующем примере предполагается, что в политику голосовой связи пользователя включено использование "Локально".</span><span class="sxs-lookup"><span data-stu-id="462bf-126">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
   ```powershell
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


