---
title: Расширитель настроек регистратора для Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 'Вы изменяете параметры устойчивости и конфигурируете следующие свойства:'
ms.openlocfilehash: 31a8504aecbc14ae2c81ad27a3aaeedbe9e40b66
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684422"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a><span data-ttu-id="5a0a5-103">Расширитель настроек регистратора для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="5a0a5-103">Registrar Settings Expander for Lync Server for 2010</span></span>
 
<span data-ttu-id="5a0a5-104">Вы изменяете параметры **устойчивости** и конфигурируете следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="5a0a5-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="5a0a5-105">Выберите из списка **связанный пул регистратора резервного копирования** .</span><span class="sxs-lookup"><span data-stu-id="5a0a5-105">Select **Associated backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="5a0a5-106">При необходимости установите флажок **Автоматический переход на другой ресурс и восстановление при сбое для голоса** .</span><span class="sxs-lookup"><span data-stu-id="5a0a5-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="5a0a5-107">Настройка **интервала обнаружения сбоев голосовой связи (сек)** и **интервала восстановления для передачи голоса (в секундах)**.</span><span class="sxs-lookup"><span data-stu-id="5a0a5-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="5a0a5-108">По умолчанию интервалы 120 секунд для обнаружения ошибок голосовой связи и 240 секунд для передачи голоса.</span><span class="sxs-lookup"><span data-stu-id="5a0a5-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="5a0a5-109">Количество секунд, которое вы определяете для интервалов отработки отказа и восстановления, должно быть тщательно протестировано для обеспечения правильной работы устойчивости.</span><span class="sxs-lookup"><span data-stu-id="5a0a5-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="5a0a5-110">Если задать для интервала значение низкий (то есть менее 120 секунд), а отработка отказа и восстановление после сбоя не работают должным образом, может возникнуть фактическая отработка отказа и восстановление размещения.</span><span class="sxs-lookup"><span data-stu-id="5a0a5-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
  <span data-ttu-id="5a0a5-111">**ОК**. Принятие и фиксация изменений, внесенных в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="5a0a5-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="5a0a5-112">**Отмена**. Отмена изменений и закрытие диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="5a0a5-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="5a0a5-113">**Справка**. Отображение этого экрана справки.</span><span class="sxs-lookup"><span data-stu-id="5a0a5-113">**Help** Displays this help screen.</span></span>
  

