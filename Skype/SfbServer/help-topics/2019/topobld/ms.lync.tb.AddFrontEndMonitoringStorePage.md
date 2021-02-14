---
title: Страница добавления хранилища мониторинга переднего плана
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
ROBOTS: NOINDEX, NOFOLLOW
description: 'Определение хранилища SQL Server для мониторинга выполняется путем настройки следующих свойств:'
ms.openlocfilehash: e867ec998e1380e70125d0ad743f83b06737758e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811669"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="a8c9b-103">Страница добавления хранилища мониторинга переднего плана</span><span class="sxs-lookup"><span data-stu-id="a8c9b-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="a8c9b-104">**Определение хранилища SQL Server для мониторинга** выполняется путем настройки следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="a8c9b-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="a8c9b-105">**Мониторинг SQL Server хранения:** выберите SQL Server полное доменное имя (и, при желании, экземпляр) в списке.</span><span class="sxs-lookup"><span data-stu-id="a8c9b-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="a8c9b-106">Нажмите **кнопку** "Создать", чтобы SQL Server определения FQDN и при желании имя экземпляра для хранения сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="a8c9b-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="a8c9b-107">Если вы хотите **добавить зеркальное отражение** базы данных для сервера мониторинга, SQL Server включить зеркальное отражение для хранения данных.</span><span class="sxs-lookup"><span data-stu-id="a8c9b-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="a8c9b-108">Выберите в списке существующее **Зеркало хранилища данных наблюдения SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a8c9b-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="a8c9b-109">Нажмите **кнопку** "Создать", чтобы SQL Server определение FQDN и при желании имя экземпляра для зеркального хранения.</span><span class="sxs-lookup"><span data-stu-id="a8c9b-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="a8c9b-110">Если вы выбрали **"Включить зеркальное SQL Server** хранения", при желании выберите "Использовать свидетель зеркального SQL Server", чтобы включить автоматическую отключку, чтобы выбрать в списке SQL Server зеркального зеркального хранения. </span><span class="sxs-lookup"><span data-stu-id="a8c9b-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="a8c9b-111">Нажмите **кнопку** "Создать", чтобы SQL Server определения FQDN и при желании имя экземпляра для зеркального хранения свидетеля.</span><span class="sxs-lookup"><span data-stu-id="a8c9b-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="a8c9b-112">Нажмите кнопку **Назад**, чтобы вернуться в предыдущее диалоговое окно определения пула.</span><span class="sxs-lookup"><span data-stu-id="a8c9b-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="a8c9b-113">После завершения ввода значений в этом диалоговом окне нажмите кнопку **Далее**, чтобы продолжить настройку.</span><span class="sxs-lookup"><span data-stu-id="a8c9b-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="a8c9b-114">Нажмите кнопку **Отмена**, чтобы отменить все изменения и завершить работу мастера.</span><span class="sxs-lookup"><span data-stu-id="a8c9b-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="a8c9b-115">Нажмите кнопку **Справка**, чтобы открыть контекстно-зависимую справку, аналогичную данной странице.</span><span class="sxs-lookup"><span data-stu-id="a8c9b-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a8c9b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a8c9b-116">See also</span></span>

[<span data-ttu-id="a8c9b-117">Связывать хранилище мониторинга с пулом переднего сервера в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a8c9b-117">Associate a monitoring store with a Front End pool in Skype for Business Server</span></span>](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
