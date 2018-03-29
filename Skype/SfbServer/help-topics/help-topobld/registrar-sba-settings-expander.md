---
title: Расширитель параметров SBA регистратора
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 'Измените параметры для функции устойчивость и настройте следующие свойства:'
ms.openlocfilehash: cdc367d1f010749e72ea2144e757d673bd41ba4a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="aa165-103">Расширитель параметров SBA регистратора</span><span class="sxs-lookup"><span data-stu-id="aa165-103">Registrar SBA Settings Expander</span></span>
 
<span data-ttu-id="aa165-104">Измените параметры для **функции устойчивость** и настройте следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="aa165-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="aa165-105">Выберите в списке **связанная служба пользователей и пул резервного регистратора** .</span><span class="sxs-lookup"><span data-stu-id="aa165-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="aa165-106">При необходимости установите флажок **Автоматическая отработка отказа и восстановления размещения для голосовой связи** .</span><span class="sxs-lookup"><span data-stu-id="aa165-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="aa165-107">Настройка **интервала обнаружения сбоев голосовой связи (сек)** и **Интервал восстановления размещения голосовой связи (сек)**.</span><span class="sxs-lookup"><span data-stu-id="aa165-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="aa165-108">По умолчанию интервалы: 120 секунд для обнаружения сбоев голосовой связи и 240 секунд для возвращения голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="aa165-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="aa165-109">Количество секунд, которые определяют интервалов отработки отказа и восстановления размещения следует тщательно проверять, чтобы убедиться, что работает устойчивости.</span><span class="sxs-lookup"><span data-stu-id="aa165-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="aa165-110">Установка интервала низкой (то есть, длиной не более 120 секунд) или отработки отказа и восстановления размещения, задайте слишком близко может привести к фактический отработки отказа и восстановления размещения, не работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="aa165-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
 <span data-ttu-id="aa165-111">**ОК**. Принятие и фиксация изменений, внесенных в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="aa165-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="aa165-112">**Отмена**. Отмена изменений и закрытие диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="aa165-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="aa165-113">**Справка**. Отображение этого экрана справки.</span><span class="sxs-lookup"><span data-stu-id="aa165-113">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="aa165-114">См. также</span><span class="sxs-lookup"><span data-stu-id="aa165-114">See also</span></span>

#### 

[<span data-ttu-id="aa165-115">Планирование устойчивости корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="aa165-115">Planning for Enterprise Voice Resiliency</span></span>](http://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)

