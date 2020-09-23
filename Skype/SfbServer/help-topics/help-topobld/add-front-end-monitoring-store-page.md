---
title: Страница добавления хранилища мониторинга переднего плана
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: 'Определение хранилища SQL Server для мониторинга выполняется путем настройки следующих свойств:'
ms.openlocfilehash: 85b8518bb533de68423dea93f259fc7b927ed9ba
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218880"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="38257-103">Страница добавления хранилища мониторинга переднего плана</span><span class="sxs-lookup"><span data-stu-id="38257-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="38257-104">**Определение хранилища SQL Server для мониторинга** выполняется путем настройки следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="38257-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="38257-105">**Хранилище SQL Server для мониторинга**: выберите в списке полное доменное имя SQL Server (и, при необходимости, экземпляр).</span><span class="sxs-lookup"><span data-stu-id="38257-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="38257-106">Нажмите кнопку **создать** , чтобы создать новое определение полного доменного имени SQL Server и (необязательно) имя экземпляра для хранилища сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="38257-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="38257-107">Установите флажок **включить зеркалирование хранилища SQL Server** , если необходимо добавить зеркальное отображение базы данных для сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="38257-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="38257-108">Выберите в списке существующее **Зеркало хранилища данных наблюдения SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="38257-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="38257-109">Нажмите кнопку **создать** , чтобы создать новое определение полного доменного имени SQL Server и (необязательно) имя экземпляра для зеркального хранилища.</span><span class="sxs-lookup"><span data-stu-id="38257-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="38257-110">Если вы выбрали **включить зеркальное отображение хранилища SQL Server**, при необходимости выберите **использовать следящий сервер ЗЕРКАЛЬного отображения SQL Server для включения автоматического перехода на другой ресурс** , чтобы выбрать в списке резервное хранилище SQL Server для зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="38257-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="38257-111">Нажмите кнопку **создать** , чтобы создать новое определение полного доменного имени SQL Server и (необязательно) имя экземпляра для хранилища-свидетеля зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="38257-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="38257-112">Нажмите кнопку **Назад**, чтобы вернуться в предыдущее диалоговое окно определения пула.</span><span class="sxs-lookup"><span data-stu-id="38257-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="38257-113">После завершения ввода значений в этом диалоговом окне нажмите кнопку **Далее**, чтобы продолжить настройку.</span><span class="sxs-lookup"><span data-stu-id="38257-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="38257-114">Нажмите кнопку **Отмена**, чтобы отменить все изменения и завершить работу мастера.</span><span class="sxs-lookup"><span data-stu-id="38257-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="38257-115">Нажмите кнопку **Справка**, чтобы открыть контекстно-зависимую справку, аналогичную данной странице.</span><span class="sxs-lookup"><span data-stu-id="38257-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="38257-116">См. также</span><span class="sxs-lookup"><span data-stu-id="38257-116">See also</span></span>

[<span data-ttu-id="38257-117">Связывание хранилища мониторинга с пулом переднего плана в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="38257-117">Associate a monitoring store with a Front End pool in Skype for Business Server 2015</span></span>](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
