---
title: Создание или изменение правила преобразования для идентификатора звонящего в Скайп для Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 'Сводка: Узнайте, как Настройка идентификатора звонящего с помощью Скайп для панели управления Business Server.'
ms.openlocfilehash: 2748677c00e74de4b26cd62494d90dc44c4b5a6a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21000157"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="6fc73-103">Создание или изменение правила преобразования для идентификатора звонящего в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="6fc73-103">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>
 
<span data-ttu-id="6fc73-104">**Сводка:** Узнайте, как Настройка идентификатора звонящего с помощью Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="6fc73-104">**Summary:** Learn how to configure Caller ID by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="6fc73-105">С Скайп для Business Server, вызываемой стороны (то есть, называемые номер телефона) может быть переведено из формата E.164 в местный формат набора номера, необходимые для _одноранговой магистральной линии связи_ (то есть, соответствующего шлюза, относиться exchange () УАТС) или магистраль SIP).</span><span class="sxs-lookup"><span data-stu-id="6fc73-105">With Skype for Business Server, the called party's phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the  _trunk peer_ (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="6fc73-106">Для этого необходимо определить одно или несколько правил преобразования для преобразования URI запроса перед переадресованием на магистральный узел.</span><span class="sxs-lookup"><span data-stu-id="6fc73-106">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>
  
<span data-ttu-id="6fc73-107">Скайп для Business Server также дает возможность также перевести телефонный номер вызывающей стороны (то есть, номер телефона, который звонит абонент из) из формата E.164 в местный формат набора номера, необходимые для одноранговой магистральной линии связи.</span><span class="sxs-lookup"><span data-stu-id="6fc73-107">Skype for Business Server also gives you the option to also translate the calling party's phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="6fc73-108">Например, можно создать правило преобразования для замены +44 в начале строки набора на 0144.</span><span class="sxs-lookup"><span data-stu-id="6fc73-108">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>
  
### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6fc73-109">Настройка идентификатора звонящего с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="6fc73-109">To configure Caller ID by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6fc73-110">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="6fc73-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="6fc73-111">На левой панели навигации щелкните **Маршрутизация голосовой связи** и **Настройка магистрали**.</span><span class="sxs-lookup"><span data-stu-id="6fc73-111">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
    
3. <span data-ttu-id="6fc73-112">На странице **Конфигурация магистрали** дважды щелкните существующую магистраль (например, **глобальную**), чтобы открыть диалоговое окно **Изменение конфигурации магистрали**.</span><span class="sxs-lookup"><span data-stu-id="6fc73-112">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
4. <span data-ttu-id="6fc73-113">Настройка представления идентификатора звонящего</span><span class="sxs-lookup"><span data-stu-id="6fc73-113">To configure caller ID presentation:</span></span>
    
   - <span data-ttu-id="6fc73-114">Чтобы выбрать одно или несколько правил из списка всех правил перевода, доступные в вашем развертывании корпоративной голосовой связи, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="6fc73-114">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="6fc73-115">В окне **Правила трансляции вызывающего номера** выберите правила, которые требуется сопоставить с магистральной линией связи, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6fc73-115">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
   - <span data-ttu-id="6fc73-116">Чтобы определить новое правило преобразования и сопоставить его с магистральной линией связи, щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="6fc73-116">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="6fc73-117">Для получения дополнительных сведений об определении новое правило в документации по развертыванию показано [Определение правил преобразования](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) .</span><span class="sxs-lookup"><span data-stu-id="6fc73-117">For details about defining a new rule, see  [Defining Translation Rules](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>
    
   - <span data-ttu-id="6fc73-118">Чтобы изменить правило преобразования, уже сопоставленное с магистральной линией связи, щелкните имя правила, а затем выберите **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="6fc73-118">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="6fc73-119">Дополнительные сведения см в документации по развертыванию [Определение правил преобразования](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) .</span><span class="sxs-lookup"><span data-stu-id="6fc73-119">For details, see [Defining Translation Rules](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>
    
   - <span data-ttu-id="6fc73-120">Чтобы скопировать существующее правило преобразования и использовать его в качестве отправной точки для определения нового правила, щелкните имя этого правила, щелкните **Копировать** и **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="6fc73-120">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="6fc73-121">Дополнительные сведения см [Определение правил преобразования](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).</span><span class="sxs-lookup"><span data-stu-id="6fc73-121">For details, see [Defining Translation Rules](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).</span></span> 
    
   - <span data-ttu-id="6fc73-122">Чтобы удалить правило преобразования из магистральной линии связи, выделите имя этого правила, а затем щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="6fc73-122">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="6fc73-123">Не сопоставляйте правила преобразования с магистральной линией связи, если вы уже настроили их для связанной одноранговой магистральной линии связи, поскольку эти два правила могут конфликтовать друг с другом.</span><span class="sxs-lookup"><span data-stu-id="6fc73-123">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span> 
  

