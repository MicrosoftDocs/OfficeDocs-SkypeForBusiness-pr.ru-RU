---
title: Расширитель параметров SBA регистратора
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
ROBOTS: NOINDEX, NOFOLLOW
description: 'Вы изменяете параметры устойчивости и конфигурируете следующие свойства:'
ms.openlocfilehash: 4297f70acfbf695d8dcfdcdb58a09d8f608add71
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41701644"
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="b3ae4-103">Расширитель параметров SBA регистратора</span><span class="sxs-lookup"><span data-stu-id="b3ae4-103">Registrar SBA Settings Expander</span></span>

<span data-ttu-id="b3ae4-104">Вы изменяете параметры **устойчивости** и конфигурируете следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="b3ae4-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>

- <span data-ttu-id="b3ae4-105">Выберите в списке **соответствующую службу пользователей и пул регистратора резервного копирования** .</span><span class="sxs-lookup"><span data-stu-id="b3ae4-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>

    <span data-ttu-id="b3ae4-106">При необходимости установите флажок **Автоматический переход на другой ресурс и восстановление при сбое для голоса** .</span><span class="sxs-lookup"><span data-stu-id="b3ae4-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>

    <span data-ttu-id="b3ae4-107">Настройка **интервала обнаружения сбоев голосовой связи (сек)** и **интервала восстановления для передачи голоса (в секундах)**.</span><span class="sxs-lookup"><span data-stu-id="b3ae4-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="b3ae4-108">По умолчанию интервалы 120 секунд для обнаружения ошибок голосовой связи и 240 секунд для передачи голоса.</span><span class="sxs-lookup"><span data-stu-id="b3ae4-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="b3ae4-109">Количество секунд, которое вы определяете для интервалов отработки отказа и восстановления, должно быть тщательно протестировано для обеспечения правильной работы устойчивости.</span><span class="sxs-lookup"><span data-stu-id="b3ae4-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="b3ae4-110">Если задать для интервала значение низкий (то есть менее 120 секунд), а отработка отказа и восстановление после сбоя не работают должным образом, может возникнуть фактическая отработка отказа и восстановление размещения.</span><span class="sxs-lookup"><span data-stu-id="b3ae4-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span>

  <span data-ttu-id="b3ae4-111">**ОК**. Принятие и фиксация изменений, внесенных в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="b3ae4-111">**OK** Accepts and commits changes to the dialog.</span></span>

  <span data-ttu-id="b3ae4-112">**Отмена**. Отмена изменений и закрытие диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="b3ae4-112">**Cancel** Discards changes and closes the dialog.</span></span>

  <span data-ttu-id="b3ae4-113">**Справка**. Отображение этого экрана справки.</span><span class="sxs-lookup"><span data-stu-id="b3ae4-113">**Help** Displays this help screen.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3ae4-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b3ae4-114">See also</span></span>

[<span data-ttu-id="b3ae4-115">Планирование устойчивости корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="b3ae4-115">Planning for Enterprise Voice Resiliency</span></span>](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
