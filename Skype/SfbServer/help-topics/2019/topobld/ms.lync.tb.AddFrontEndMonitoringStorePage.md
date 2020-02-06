---
title: Страница добавления хранилища мониторинга переднего плана
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Вы определяете хранилище SQL Server для мониторинга, настраивая следующие свойства:'
ms.openlocfilehash: 1d6e9d4bbc795707105a6282ac004dde5c264171
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798536"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="df5ce-103">Страница добавления хранилища мониторинга переднего плана</span><span class="sxs-lookup"><span data-stu-id="df5ce-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="df5ce-104">Вы **определяете хранилище SQL Server для мониторинга** , настраивая следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="df5ce-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="df5ce-105">**Наблюдение за хранилищем SQL Server**: выберите в списке полное доменное имя SQL Server (и, при необходимости, экземпляр).</span><span class="sxs-lookup"><span data-stu-id="df5ce-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="df5ce-106">Нажмите кнопку **создать** , чтобы создать новое определение полного доменного имени SQL Server и (необязательно) имя экземпляра для хранилища серверов мониторинга.</span><span class="sxs-lookup"><span data-stu-id="df5ce-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="df5ce-107">Установите флажок **включить зеркальное отображение хранилища SQL Server** , если вы хотите добавить зеркальное отображение базы данных для сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="df5ce-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="df5ce-108">Выберите существующее **зеркало хранилища SQL Server для мониторинга** из списка.</span><span class="sxs-lookup"><span data-stu-id="df5ce-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="df5ce-109">Нажмите кнопку **создать** , чтобы создать новое определение полного доменного имени SQL Server и (необязательно) имя экземпляра для зеркального хранилища.</span><span class="sxs-lookup"><span data-stu-id="df5ce-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="df5ce-110">Если вы выбрали **включить зеркальное отображение хранилища SQL Server**, при необходимости установите флажок **использовать следящий сервер SQL Server, чтобы включить автоматический переход на другой ресурс** , чтобы выбрать в списке хранилище СВИДЕТЕЛЯ зеркального отображения SQL Server.</span><span class="sxs-lookup"><span data-stu-id="df5ce-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="df5ce-111">Нажмите кнопку **создать** , чтобы создать новое определение полного доменного имени SQL Server и (необязательно) имя экземпляра для хранилища следящего сервера зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="df5ce-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="df5ce-112">Для возврата к предыдущему диалоговому окну определения пула нажмите кнопку **Назад**.</span><span class="sxs-lookup"><span data-stu-id="df5ce-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="df5ce-113">После того как вы закончите ввод параметров для этого диалогового окна, нажмите кнопку **Далее** , чтобы продолжить настройку.</span><span class="sxs-lookup"><span data-stu-id="df5ce-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="df5ce-114">Нажмите кнопку **Отмена** , чтобы отменить все изменения и завершить работу мастера.</span><span class="sxs-lookup"><span data-stu-id="df5ce-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="df5ce-115">Для доступа к контекстно-зависимой справке, аналогичной данной странице, нажмите кнопку **Справка**.</span><span class="sxs-lookup"><span data-stu-id="df5ce-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="df5ce-116">См. также</span><span class="sxs-lookup"><span data-stu-id="df5ce-116">See also</span></span>

[<span data-ttu-id="df5ce-117">Связывание хранилища мониторинга с внешним интерфейсом в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="df5ce-117">Associate a monitoring store with a Front End pool in Skype for Business Server</span></span>](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
