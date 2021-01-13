---
title: Create or modify a translation rule for caller ID presentation in Skype for Business Server
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
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: Сводка. Сведения о настройке ИД вызываемой стороны с помощью панели управления Skype для бизнеса Server.
ms.openlocfilehash: ca1451a051a1c9053b88861222d2c4d42c5d555b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804189"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="57cc1-103">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="57cc1-103">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="57cc1-104">**Сводка:** Learn how to configure Caller ID by using the Skype for Business Server Control Panel.</span><span class="sxs-lookup"><span data-stu-id="57cc1-104">**Summary:** Learn how to configure Caller ID by using the Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="57cc1-105">В Skype для бизнеса Server номер телефона звонящей стороны (то есть номер телефона) можно перевести из формата E.164 в локальный формат набора номера, требующийся магистральным одноранговом серверу  _(то_ есть связанному шлюзу, УАЧС или магистрали SIP).</span><span class="sxs-lookup"><span data-stu-id="57cc1-105">With Skype for Business Server, the called party's phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the  _trunk peer_ (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="57cc1-106">Для этого необходимо определить одно или несколько правил преобразования для преобразования URI запроса перед переадресованием на магистральный узел.</span><span class="sxs-lookup"><span data-stu-id="57cc1-106">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<span data-ttu-id="57cc1-107">Skype для бизнеса Server также позволяет переводить телефонный номер вызываемой стороны (то есть номер телефона, с который звонит звонящая) из формата E.164 в формат местного набора номера, который требуется магистральным одноранговом серверу.</span><span class="sxs-lookup"><span data-stu-id="57cc1-107">Skype for Business Server also gives you the option to also translate the calling party's phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="57cc1-108">Например, можно написать правило преобразования для удаления +44 из начала строки набора и замены на 0144.</span><span class="sxs-lookup"><span data-stu-id="57cc1-108">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="57cc1-109">Настройка ИД вызываемой стороны с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="57cc1-109">To configure Caller ID by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="57cc1-110">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="57cc1-110">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="57cc1-111">В левой панели навигации последовательно выберите пункты **Маршрутизация голосовой связи** и **Конфигурация магистрали**.</span><span class="sxs-lookup"><span data-stu-id="57cc1-111">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="57cc1-112">На странице **Конфигурация магистрали** дважды щелкните существующую магистраль (например, **глобальную**), чтобы открыть диалоговое окно **Изменение конфигурации магистрали**.</span><span class="sxs-lookup"><span data-stu-id="57cc1-112">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

4. <span data-ttu-id="57cc1-113">Настройка представления идентификатора звонящего</span><span class="sxs-lookup"><span data-stu-id="57cc1-113">To configure caller ID presentation:</span></span>

   - <span data-ttu-id="57cc1-114">Чтобы выбрать одно или несколько правил из списка всех правил трансляции, доступных в развертывании Корпоративная голосовая связь, нажмите кнопку **"Выбрать".**</span><span class="sxs-lookup"><span data-stu-id="57cc1-114">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="57cc1-115">В окне **Правила трансляции вызывающего номера** выберите правила, которые требуется сопоставить с магистральной линией связи, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="57cc1-115">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

   - <span data-ttu-id="57cc1-116">Чтобы определить новое правило преобразования и сопоставить его с магистральной линией связи, щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="57cc1-116">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="57cc1-117">Подробные сведения об определении нового правила см. в документации по развертыванию "  [Определение](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) правил трансляции".</span><span class="sxs-lookup"><span data-stu-id="57cc1-117">For details about defining a new rule, see  [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

   - <span data-ttu-id="57cc1-118">Чтобы изменить правило преобразования, которое уже сопоставлено с магистралью, щелкните имя правила, затем нажмите кнопку **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="57cc1-118">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="57cc1-119">Дополнительные сведения см. в разделе [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="57cc1-119">For details, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

   - <span data-ttu-id="57cc1-120">Чтобы скопировать существующее правило преобразования и использовать его в качестве отправной точки для определения нового правила, щелкните имя правила и нажмите кнопку **Копировать**, а затем кнопку **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="57cc1-120">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="57cc1-121">Дополнительные сведения см. в разделе [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).</span><span class="sxs-lookup"><span data-stu-id="57cc1-121">For details, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).</span></span>

   - <span data-ttu-id="57cc1-122">Чтобы удалить правило преобразования из магистральной линии связи, выделите имя этого правила, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="57cc1-122">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="57cc1-123">Не сопоставляйте правила преобразования с магистральной линией связи, если вы уже настроили их для связанной одноранговой магистральной линии связи, поскольку эти два правила могут конфликтовать друг с другом.</span><span class="sxs-lookup"><span data-stu-id="57cc1-123">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>


