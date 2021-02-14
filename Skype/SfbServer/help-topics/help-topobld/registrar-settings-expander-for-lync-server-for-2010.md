---
title: Расширитель настроек регистратора для Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 'Измените параметры для функции Устойчивость и настройте следующие свойства:'
ms.openlocfilehash: 92df9deeba1287dab4dc7d84b089fa81ca2e51ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818329"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a><span data-ttu-id="385a7-103">Расширитель параметров регистратора для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="385a7-103">Registrar Settings Expander for Lync Server for 2010</span></span>
 
<span data-ttu-id="385a7-104">Измените параметры для функции **Устойчивость** и настройте следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="385a7-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="385a7-105">Выберите в списке значение **Связанный пул резервного регистратора**.</span><span class="sxs-lookup"><span data-stu-id="385a7-105">Select **Associated backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="385a7-106">При необходимости установите флажок **Автоматическая обработка отказов и восстановление после отказа для голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="385a7-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="385a7-p101">Настройте параметры **Интервал обнаружения неполадок голосовой связи (сек)** и **Интервал восстановления после сбоя голосовой связи (сек)**. По умолчанию эти значения составляют 120 секунд для интервала обнаружения неполадок голосовой связи и 240 секунд для интервала восстановления после сбоя голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="385a7-p101">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**. By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="385a7-p102">Следует тщательно протестировать задаваемые значения интервалов обнаружения неполадок и восстановления после сбоя, чтобы гарантировать правильную работу функции устойчивости. Задание слишком малого интервала (менее 120 секунд) или незначительно различающихся интервалов обнаружения неполадок и восстановления после сбоя может привести к неправильной работе соответствующих функций.</span><span class="sxs-lookup"><span data-stu-id="385a7-p102">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected. Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
  <span data-ttu-id="385a7-111">При нажатии кнопки **ОК** выполняется принятие и сохранение изменений в этом диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="385a7-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="385a7-112">При нажатии кнопки **Отмена** изменения отменяются, а диалоговое окно закрывается.</span><span class="sxs-lookup"><span data-stu-id="385a7-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="385a7-113">При нажатии кнопки **Справка** отображается данный экран справки.</span><span class="sxs-lookup"><span data-stu-id="385a7-113">**Help** Displays this help screen.</span></span>
  

