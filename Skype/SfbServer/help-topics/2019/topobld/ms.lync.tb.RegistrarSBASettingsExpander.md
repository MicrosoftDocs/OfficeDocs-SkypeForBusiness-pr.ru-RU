---
title: Расширитель параметров SBA регистратора
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
ROBOTS: NOINDEX, NOFOLLOW
description: 'Измените параметры для функции устойчивость и настройте следующие свойства:'
ms.openlocfilehash: 48d5219d690a383ba46065a1287efbadcb455fef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919796"
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="c53e1-103">Расширитель параметров SBA регистратора</span><span class="sxs-lookup"><span data-stu-id="c53e1-103">Registrar SBA Settings Expander</span></span>

<span data-ttu-id="c53e1-104">Измените параметры для **функции устойчивость** и настройте следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="c53e1-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>

- <span data-ttu-id="c53e1-105">Выберите в списке **связанная служба пользователей и пул резервного регистратора** .</span><span class="sxs-lookup"><span data-stu-id="c53e1-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>

    <span data-ttu-id="c53e1-106">При необходимости установите флажок **Автоматическая отработка отказа и восстановления размещения для голосовой связи** .</span><span class="sxs-lookup"><span data-stu-id="c53e1-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>

    <span data-ttu-id="c53e1-107">Настройка **интервала обнаружения сбоев голосовой связи (сек)** и **Интервал восстановления размещения голосовой связи (сек)**.</span><span class="sxs-lookup"><span data-stu-id="c53e1-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="c53e1-108">По умолчанию интервалы: 120 секунд для обнаружения сбоев голосовой связи и 240 секунд для возвращения голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="c53e1-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="c53e1-109">Количество секунд, которые определяют интервалов отработки отказа и восстановления размещения следует тщательно проверять, чтобы убедиться, что работает устойчивости.</span><span class="sxs-lookup"><span data-stu-id="c53e1-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="c53e1-110">Установка интервала низкой (то есть, длиной не более 120 секунд) или отработки отказа и восстановления размещения, задайте слишком близко может привести к фактический отработки отказа и восстановления размещения, не работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="c53e1-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span>

  <span data-ttu-id="c53e1-111">**ОК**. Принятие и фиксация изменений, внесенных в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="c53e1-111">**OK** Accepts and commits changes to the dialog.</span></span>

  <span data-ttu-id="c53e1-112">**Отмена**. Отмена изменений и закрытие диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="c53e1-112">**Cancel** Discards changes and closes the dialog.</span></span>

  <span data-ttu-id="c53e1-113">**Справка**. Отображение этого экрана справки.</span><span class="sxs-lookup"><span data-stu-id="c53e1-113">**Help** Displays this help screen.</span></span>

## <a name="see-also"></a><span data-ttu-id="c53e1-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c53e1-114">See also</span></span>

[<span data-ttu-id="c53e1-115">Планирование устойчивости корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="c53e1-115">Planning for Enterprise Voice Resiliency</span></span>](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
