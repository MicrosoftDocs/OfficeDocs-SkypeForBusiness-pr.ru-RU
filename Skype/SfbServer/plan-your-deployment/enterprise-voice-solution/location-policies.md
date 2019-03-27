---
title: Планирование политик расположения Скайп для Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: Прочтите этот раздел, чтобы узнать о планировании политики расположения для развертывания усовершенствованные экстренных служб (E9-1-1) в Скайп Business Server Enterprise Voice.
ms.openlocfilehash: 6717d6b7940ccf9cf7de403797d8bd4712f18144
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878023"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a><span data-ttu-id="cd2d7-103">Планирование политик расположения Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="cd2d7-103">Plan location policies for Skype for Business Server</span></span>
 
<span data-ttu-id="cd2d7-104">Прочтите этот раздел, чтобы узнать о планировании политики расположения для развертывания усовершенствованные экстренных служб (E9-1-1) в Скайп Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cd2d7-105">Скайп для Business Server теперь поддерживает конфигурации нескольких аварийного номера для клиента.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="cd2d7-106">Если вы хотите настроить несколько аварийного номера, необходимо выполнить сведения в [Планирование нескольких аварийного номера в Скайп для Business Server](multiple-emergency-numbers.md) и [настроить несколько аварийного номера в Скайп для бизнеса](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="cd2d7-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="cd2d7-107">Создание политик расположения с помощью Скайп для панели управления бизнеса или с помощью командлета [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="cd2d7-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="cd2d7-108">Дополнительные сведения можно [Создать политики расположения в Скайп для Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="cd2d7-108">For more information, see [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="cd2d7-109">Все политики расположений содержат следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="cd2d7-110">**Разрешить расширенные службы экстренного вызова**</span><span class="sxs-lookup"><span data-stu-id="cd2d7-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="cd2d7-111">Если этого параметр включен, для клиента включена поддержка E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="cd2d7-112">При регистрации клиента, пытается получить местоположение из службы сведения о расположении и будут включены сведения о местоположении как часть экстренных вызовов.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="cd2d7-113">**Расположение**</span><span class="sxs-lookup"><span data-stu-id="cd2d7-113">**Location**</span></span>
  
<span data-ttu-id="cd2d7-114">Эта настройка используется только в том случае, если включен параметр **Разрешить расширенные службы экстренного вызова**. </span><span class="sxs-lookup"><span data-stu-id="cd2d7-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="cd2d7-115">Чтобы определить поведение клиентов, можно настроить параметр **Расположение** следующим образом:   </span><span class="sxs-lookup"><span data-stu-id="cd2d7-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="cd2d7-116">Если задать значение **Нет**, расположение не будет запрашиваться у пользователя.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="cd2d7-117">Если задать значение **Да**, расположение будет запрашиваться у пользователя, но он сможет отклонить запрос.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="cd2d7-p104">Если задать для параметра значение **Заявление об отказе**, расположение будет запрашиваться у пользователя и при попытке отклонить запрос будет выводиться уведомление об отказе. В любом случае пользователь сможет использовать клиент.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-p104">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cd2d7-p105">Текст заявления не отображается, если пользователь вручную вводит расположение, прежде чем получить доступ к E9-1-1. Обновленный текст заявления об отказе не будет отображаться для пользователей, которые уже просмотрели заявление. </span><span class="sxs-lookup"><span data-stu-id="cd2d7-p105">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="cd2d7-122">**Заявление об отказе расширенных экстренных служб**</span><span class="sxs-lookup"><span data-stu-id="cd2d7-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="cd2d7-123">Этот параметр задает заявление об отказе, которое будет отображаться для пользователей, если они отклоняют запрос расположения.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="cd2d7-124">В Скайп Business Server можно использовать политики расположения для установки различных заявления об отказе для разных регионах или различных групп пользователей.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="cd2d7-125">**Строка набора аварийного номера (номер экстренного вызова)**</span><span class="sxs-lookup"><span data-stu-id="cd2d7-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="cd2d7-126">Эта строка номера (меньше начальные «+», но включая любые нормализации, сделанные пользователем абонентская) означает, что вызов является экстренных вызовов.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="cd2d7-127">На клиенте **строка набора аварийного номера** обеспечивает включение в вызов данных о местоположении и информации для обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cd2d7-128">Если ваша организация не использует префикс доступа к внешней линии, не требуется создавать соответствующий абонентская группа правила нормализации, добавляющий «+» для 911 строки перед отправкой звонка для маршрутизации исходящих вызовов на сервере под управлением Скайп для Business Server; «+» будут автоматически должны добавляться в начало с Скайп для клиента Business из-за политики расположения.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="cd2d7-129">Тем не менее, если сайт использует префикс внешнего доступа, необходимо добавить правила нормализации применение политики абонентская группа, который удаляет префикс внешнего доступа и добавляет «+».</span><span class="sxs-lookup"><span data-stu-id="cd2d7-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="cd2d7-130">К примеру, если ваше расположение использует префикс внешнего доступа 9 и пользователь набирает 9 911 для помещения экстренных вызовов, клиент будет использовать его политику абонентская группа для нормализации это для +911 перед вычислением набранный номер маршруты в профиль расположения вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="cd2d7-131">**Маски строки набора аварийного номера (маска номера экстренного вызова)**</span><span class="sxs-lookup"><span data-stu-id="cd2d7-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="cd2d7-132">Разделенный точками с запятыми список строк набора номера, которое будет преобразовано в указанной **Строки набора аварийного**.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="cd2d7-133">К примеру можно добавить 112, которого — номер экстренной службы для большинства Европа.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="cd2d7-134">Посещение Скайп для корпоративных пользователей из Европы могут не знать, что 911 — номер экстренного США, но они могут позвонить 112 и это действие.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="cd2d7-135">Как в строке аварийного номера исключение «+» перед каждым числом и используйте коды доступа к внешней линии, убедитесь, что существует правил нормализации в абонентской политике для удаления off цифры код доступа.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="cd2d7-136">**Использование ТСОП**</span><span class="sxs-lookup"><span data-stu-id="cd2d7-136">**PSTN usage**</span></span>
  
<span data-ttu-id="cd2d7-137">Имя режима работы с ТСОП, содержащее пути маршрутизации, определяющие, через какую магистраль SIP, шлюз ТСОП или шлюз ELIN будут передаваться звонки в аварийные службы.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cd2d7-138">Только один раз может быть назначен в политику расположения.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="cd2d7-139">Этот режим работы с ТСОП переопределяет ТСОП, привязываемых к политике голосовой связи, но применяется только к вызовам, выполнившим к строке аварийного номера или к одной из масок аварийного номера строки.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="cd2d7-140">**URI уведомления**</span><span class="sxs-lookup"><span data-stu-id="cd2d7-140">**Notification URI**</span></span>
  
<span data-ttu-id="cd2d7-p111">Задает один или несколько URI SIP персонала службы безопасности, которые получают уведомление в виде мгновенного сообщения при отправке звонка в аварийную службу. Этот параметр поддерживает группы рассылки.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-p111">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>
  
 <span data-ttu-id="cd2d7-143">**Идентификатор URI конференции**</span><span class="sxs-lookup"><span data-stu-id="cd2d7-143">**Conference URI**</span></span>
  
<span data-ttu-id="cd2d7-144">Задает прямой внутренний номер (как правило, номер службы безопасности), по которому выполнятся подключение конференц-связи при отправке звонка в аварийную службу.  </span><span class="sxs-lookup"><span data-stu-id="cd2d7-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="cd2d7-145">**Режим конференции**</span><span class="sxs-lookup"><span data-stu-id="cd2d7-145">**Conference Mode**</span></span>
  
<span data-ttu-id="cd2d7-146">Указывает, будет ли URI конференции включаться в вызов аварийной службы в режиме односторонней или двусторонней связи. </span><span class="sxs-lookup"><span data-stu-id="cd2d7-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="cd2d7-147">**Интервал обновления данных расположения**</span><span class="sxs-lookup"><span data-stu-id="cd2d7-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="cd2d7-148">Указывает количество времени (в часах) между запросы клиентов для обновления расположение из службы сведения о расположении.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="cd2d7-149">The value can be set to any value between 1 and 12.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="cd2d7-150">The default value is 4.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-150">The default value is 4.</span></span>
  

