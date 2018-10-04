---
title: Расширитель настроек регистратора для Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 'Измените параметры для функции устойчивость и настройте следующие свойства:'
ms.openlocfilehash: 5d6fffdadeb96ed72caf9478cbcaefe754d8e24c
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374057"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a><span data-ttu-id="d6903-103">Расширитель настроек регистратора для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="d6903-103">Registrar Settings Expander for Lync Server for 2010</span></span>
 
<span data-ttu-id="d6903-104">Измените параметры для **функции устойчивость** и настройте следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="d6903-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="d6903-105">Выберите в списке **связанный пул резервного регистратора** .</span><span class="sxs-lookup"><span data-stu-id="d6903-105">Select **Associated backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="d6903-106">При необходимости установите флажок **Автоматическая отработка отказа и восстановления размещения для голосовой связи** .</span><span class="sxs-lookup"><span data-stu-id="d6903-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="d6903-107">Настройка **интервала обнаружения сбоев голосовой связи (сек)** и **Интервал восстановления размещения голосовой связи (сек)**.</span><span class="sxs-lookup"><span data-stu-id="d6903-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="d6903-108">По умолчанию интервалы: 120 секунд для обнаружения сбоев голосовой связи и 240 секунд для возвращения голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="d6903-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="d6903-109">Количество секунд, которые определяют интервалов отработки отказа и восстановления размещения следует тщательно проверять, чтобы убедиться, что работает устойчивости.</span><span class="sxs-lookup"><span data-stu-id="d6903-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="d6903-110">Установка интервала низкой (то есть, длиной не более 120 секунд) или отработки отказа и восстановления размещения, задайте слишком близко может привести к фактический отработки отказа и восстановления размещения, не работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="d6903-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
  <span data-ttu-id="d6903-111">**ОК**. Принятие и фиксация изменений, внесенных в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="d6903-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="d6903-112">**Отмена**. Отмена изменений и закрытие диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="d6903-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="d6903-113">**Справка**. Отображение этого экрана справки.</span><span class="sxs-lookup"><span data-stu-id="d6903-113">**Help** Displays this help screen.</span></span>
  

