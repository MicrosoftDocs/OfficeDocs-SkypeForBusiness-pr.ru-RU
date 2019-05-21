---
title: Настройка маршрута голосовой связи E9-1-1 в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Настройте Голосовые маршруты E9 1-1 в Skype для бизнеса Server Enterprise.
ms.openlocfilehash: 0ef8b1ba2b64c74cb2166c90dfdccf134df42252
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303456"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a><span data-ttu-id="23f8b-103">Настройка маршрута голосовой связи E9-1-1 в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="23f8b-103">Configure an E9-1-1 voice route in Skype for Business Server</span></span>
 
<span data-ttu-id="23f8b-104">Настройте Голосовые маршруты E9 1-1 в Skype для бизнеса Server Enterprise.</span><span class="sxs-lookup"><span data-stu-id="23f8b-104">Configure E9-1-1 voice routes in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="23f8b-105">Чтобы развернуть E9-1-1, сначала необходимо настроить маршрут голосовой связи для выполнения экстренных вызовов.</span><span class="sxs-lookup"><span data-stu-id="23f8b-105">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="23f8b-106">Подробнее о создании голосовых маршрутов можно узнать [в статьях создание и изменение голосовых маршрутов в Skype для бизнеса](create-or-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="23f8b-106">For details about creating voice routes, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span> <span data-ttu-id="23f8b-107">Можно определить более одного маршрута, если, например, развертывание включает основной магистральный канал SIP и дополнительный магистральный канал SIP.</span><span class="sxs-lookup"><span data-stu-id="23f8b-107">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="23f8b-108">Чтобы включить информацию о местоположении в приглашение E9-1-1 INVITE, необходимо настроить магистральный канал SIP, который служит для подключения к поставщику службы E9-1-1 для маршрутизации экстренных вызовов через шлюз.</span><span class="sxs-lookup"><span data-stu-id="23f8b-108">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="23f8b-109">Для этого установите для флага EnablePIDFLOSupport в командлете **Set-CsTrunkConfiguration** значение True.</span><span class="sxs-lookup"><span data-stu-id="23f8b-109">To do this, set the EnablePIDFLOSupport flag on the **Set-CsTrunkConfiguration** cmdlet to True.</span></span> <span data-ttu-id="23f8b-110">Значение по умолчанию для EnablePIDFLOSupport — False.</span><span class="sxs-lookup"><span data-stu-id="23f8b-110">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="23f8b-111">Например: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` не нужно включать получение расположений для ШЛЮЗов коммутируемой телефонной сети (PSTN) и ШЛЮЗОВ (Елин).</span><span class="sxs-lookup"><span data-stu-id="23f8b-111">For example: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>
  
### <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="23f8b-112">Настройка маршрута голосовой связи E9-1-1</span><span class="sxs-lookup"><span data-stu-id="23f8b-112">To configure an E9-1-1 voice route</span></span>

1. <span data-ttu-id="23f8b-113">Выполните вход в систему компьютера с использованием учетной записи, которая является членом группы RTCUniversalServerAdmins или членом роли администратора CsVoiceAdministrator.</span><span class="sxs-lookup"><span data-stu-id="23f8b-113">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>
    
2.  <span data-ttu-id="23f8b-114">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="23f8b-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="23f8b-115">Выполните следующий командлет, чтобы создать новую запись об использовании ТСОП.</span><span class="sxs-lookup"><span data-stu-id="23f8b-115">Run the following cmdlet to create a new PSTN usage record.</span></span> 
    
    <span data-ttu-id="23f8b-116">Это должно быть то же самое имя, которое будет использоваться для параметра **ТСОП** в политике определения местоположения.</span><span class="sxs-lookup"><span data-stu-id="23f8b-116">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="23f8b-117">Хотя развертывание будет включать несколько записей об использовании телефона, в следующем примере показано, как добавить "Использование экстренных вызовов" в текущий список доступных использований ТСОП.</span><span class="sxs-lookup"><span data-stu-id="23f8b-117">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="23f8b-118">Подробности можно найти [в разделе Настройка политик голосовой связи, записей использования КТСОП и голосовых маршрутов в Skype для бизнеса](voice-and-pstn.md).</span><span class="sxs-lookup"><span data-stu-id="23f8b-118">For details, see [Configure voice policies, PSTN usage records, and voice routes in Skype for Business](voice-and-pstn.md).</span></span>
    
   ```
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. <span data-ttu-id="23f8b-119">Выполните следующий командлет, чтобы создать новый маршрут голосовой связи с помощью записи об использовании ТСОП, созданной на предыдущем этапе.</span><span class="sxs-lookup"><span data-stu-id="23f8b-119">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="23f8b-120">Шаблон номера должен соответствовать шаблону номера, который используется в параметре **Строка набора номера для экстренной связи** политики определения местоположения.</span><span class="sxs-lookup"><span data-stu-id="23f8b-120">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="23f8b-121">Знак "+" нужен, так как в Skype для бизнеса для вызова экстренной помощи добавляется символ "+".</span><span class="sxs-lookup"><span data-stu-id="23f8b-121">A "+" sign is needed because Skype for Business adds "+" to emergency calls.</span></span> <span data-ttu-id="23f8b-122">"Co1-pstngateway-1" — это идентификатор службы магистрального канала SIP для поставщика службы E9-1-1 или для идентификатора службы шлюза ELIN.</span><span class="sxs-lookup"><span data-stu-id="23f8b-122">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="23f8b-123">В следующем примере в качестве имени маршрута голосовой связи используется EmergencyRoute.</span><span class="sxs-lookup"><span data-stu-id="23f8b-123">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
   ```
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. <span data-ttu-id="23f8b-124">Кроме того, для подключения к магистрали по протоколу SIP рекомендуется запустить следующий командлет, чтобы создать локальный маршрут для звонков, которые не обрабатываются с помощью канала SIP поставщика услуг E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="23f8b-124">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider's SIP trunk.</span></span> <span data-ttu-id="23f8b-125">Этот маршрут будет использоваться, если подключение к поставщику службы E9-1-1 недоступно.</span><span class="sxs-lookup"><span data-stu-id="23f8b-125">This route will be used if the connection to the E9-1-1 service provider is not available.</span></span> 
    
    <span data-ttu-id="23f8b-126">В следующем примере предполагается, что в политику голосовой связи пользователя включено использование "Локально".</span><span class="sxs-lookup"><span data-stu-id="23f8b-126">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
   ```
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


