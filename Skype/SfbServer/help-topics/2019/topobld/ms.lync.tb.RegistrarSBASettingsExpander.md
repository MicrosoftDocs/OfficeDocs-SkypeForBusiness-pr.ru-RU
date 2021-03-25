---
title: Расширитель параметров SBA регистратора
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
ROBOTS: NOINDEX, NOFOLLOW
description: 'Измените параметры для функции Устойчивость и настройте следующие свойства:'
ms.openlocfilehash: c53aa49771a7e2c1a239319901059dc5d22b7eaf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121032"
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="cc3ee-103">Расширитель параметров SBA регистратора</span><span class="sxs-lookup"><span data-stu-id="cc3ee-103">Registrar SBA Settings Expander</span></span>

<span data-ttu-id="cc3ee-104">Измените параметры для функции **Устойчивость** и настройте следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="cc3ee-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>

- <span data-ttu-id="cc3ee-105">Выберите в списке значение **Связанная служба пользователей и пул резервного регистратора**</span><span class="sxs-lookup"><span data-stu-id="cc3ee-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>

    <span data-ttu-id="cc3ee-106">При необходимости установите флажок **Автоматическая обработка отказов и восстановление после отказа для голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="cc3ee-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>

    <span data-ttu-id="cc3ee-p101">Настройте параметры **Интервал обнаружения неполадок голосовой связи (сек)** и **Интервал восстановления после сбоя голосовой связи (сек)**. По умолчанию эти значения составляют 120 секунд для интервала обнаружения неполадок голосовой связи и 240 секунд для интервала восстановления после сбоя голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="cc3ee-p101">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**. By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="cc3ee-p102">Следует тщательно протестировать задаваемые значения интервалов обнаружения неполадок и восстановления после сбоя, чтобы гарантировать правильную работу функции устойчивости. Задание слишком малого интервала (менее 120 секунд) или незначительно различающихся интервалов обнаружения неполадок и восстановления после сбоя может привести к неправильной работе соответствующих функций.</span><span class="sxs-lookup"><span data-stu-id="cc3ee-p102">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected. Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span>

  <span data-ttu-id="cc3ee-111">При нажатии кнопки **ОК** выполняется принятие и сохранение изменений в этом диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="cc3ee-111">**OK** Accepts and commits changes to the dialog.</span></span>

  <span data-ttu-id="cc3ee-112">При нажатии кнопки **Отмена** изменения отменяются, а диалоговое окно закрывается.</span><span class="sxs-lookup"><span data-stu-id="cc3ee-112">**Cancel** Discards changes and closes the dialog.</span></span>

  <span data-ttu-id="cc3ee-113">При нажатии кнопки **Справка** отображается данный экран справки.</span><span class="sxs-lookup"><span data-stu-id="cc3ee-113">**Help** Displays this help screen.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc3ee-114">См. также</span><span class="sxs-lookup"><span data-stu-id="cc3ee-114">See also</span></span>

[<span data-ttu-id="cc3ee-115">Планирование устойчивости корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="cc3ee-115">Planning for Enterprise Voice Resiliency</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency)