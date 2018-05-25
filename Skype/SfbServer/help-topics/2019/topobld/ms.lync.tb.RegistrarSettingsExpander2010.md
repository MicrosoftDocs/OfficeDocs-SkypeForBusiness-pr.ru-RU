---
title: Расширитель настроек регистратора для Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 'Измените параметры для функции устойчивость и настройте следующие свойства:'
ms.openlocfilehash: 88a2d75ff6f0225328a0f27743e0129950a5ca91
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2018
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a><span data-ttu-id="bb722-103">Расширитель настроек регистратора для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="bb722-103">Registrar Settings Expander for Lync Server for 2010</span></span>
 
<span data-ttu-id="bb722-104">Измените параметры для **функции устойчивость** и настройте следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="bb722-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="bb722-105">Выберите в списке **связанный пул резервного регистратора** .</span><span class="sxs-lookup"><span data-stu-id="bb722-105">Select **Associated backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="bb722-106">При необходимости установите флажок **Автоматическая отработка отказа и восстановления размещения для голосовой связи** .</span><span class="sxs-lookup"><span data-stu-id="bb722-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="bb722-107">Настройка **интервала обнаружения сбоев голосовой связи (сек)** и **Интервал восстановления размещения голосовой связи (сек)**.</span><span class="sxs-lookup"><span data-stu-id="bb722-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="bb722-108">По умолчанию интервалы: 120 секунд для обнаружения сбоев голосовой связи и 240 секунд для возвращения голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="bb722-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="bb722-109">Количество секунд, которые определяют интервалов отработки отказа и восстановления размещения следует тщательно проверять, чтобы убедиться, что работает устойчивости.</span><span class="sxs-lookup"><span data-stu-id="bb722-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="bb722-110">Установка интервала низкой (то есть, длиной не более 120 секунд) или отработки отказа и восстановления размещения, задайте слишком близко может привести к фактический отработки отказа и восстановления размещения, не работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="bb722-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
 <span data-ttu-id="bb722-111">**ОК**. Принятие и фиксация изменений, внесенных в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="bb722-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="bb722-112">**Отмена**. Отмена изменений и закрытие диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="bb722-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="bb722-113">**Справка**. Отображение этого экрана справки.</span><span class="sxs-lookup"><span data-stu-id="bb722-113">**Help** Displays this help screen.</span></span>
  

