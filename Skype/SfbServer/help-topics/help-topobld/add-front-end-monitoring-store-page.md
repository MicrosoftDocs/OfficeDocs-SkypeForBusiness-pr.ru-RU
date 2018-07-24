---
title: Добавление хранилища мониторинга переднего плана
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: 'Вы определение хранилища SQL Server для мониторинга, настроив следующие свойства:'
ms.openlocfilehash: ea2a477bc970f0f431f2290b40bcb2b100ccc942
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967721"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="c0e9b-103">Добавление хранилища мониторинга переднего плана</span><span class="sxs-lookup"><span data-stu-id="c0e9b-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="c0e9b-104">Вы **Определение хранилища SQL Server для мониторинга** , настроив следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="c0e9b-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="c0e9b-105">**Хранилища мониторинга SQL Server**: выберите в списке полное доменное имя сервера SQL Server (и, при необходимости экземпляр).</span><span class="sxs-lookup"><span data-stu-id="c0e9b-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="c0e9b-106">Нажмите кнопку **Создать** , чтобы создать новое определение полного доменного ИМЕНИ сервера SQL, а также имя экземпляра для хранилища сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="c0e9b-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="c0e9b-107">Установите флажок **Включить хранилища SQL Server зеркального отображения** , если вы хотите добавить зеркальное отображение базы данных для сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="c0e9b-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="c0e9b-108">Выберите в списке существующий **зеркального хранилища мониторинга SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="c0e9b-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="c0e9b-109">Нажмите кнопку **Создать** , чтобы создать новое определение полного доменного ИМЕНИ сервера SQL, а также имя экземпляра для зеркального хранилища.</span><span class="sxs-lookup"><span data-stu-id="c0e9b-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="c0e9b-110">Если выбрано **зеркальное отображение хранилища SQL Server для включения**, при необходимости установите **следящий сервер для включения автоматического переключения зеркального отображения с помощью SQL Server** для выбора сервера SQL Server зеркальное отображение хранилища-свидетеля из списка.</span><span class="sxs-lookup"><span data-stu-id="c0e9b-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="c0e9b-111">Нажмите кнопку **Создать** , чтобы создать новое определение полного доменного ИМЕНИ сервера SQL, а также имя экземпляра для хранилища-свидетеля зеркалирования.</span><span class="sxs-lookup"><span data-stu-id="c0e9b-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="c0e9b-112">Для возврата к предыдущему диалоговому окну определения пула нажмите кнопку **Назад**.</span><span class="sxs-lookup"><span data-stu-id="c0e9b-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="c0e9b-113">После завершения ввода значений в этом диалоговом окне продолжить настройку, нажмите кнопку **Далее** .</span><span class="sxs-lookup"><span data-stu-id="c0e9b-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="c0e9b-114">Нажмите кнопку **Отмена** , чтобы отменить все изменения и завершить работу мастера.</span><span class="sxs-lookup"><span data-stu-id="c0e9b-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="c0e9b-115">Для доступа к контекстно-зависимой справке, аналогичной данной странице, нажмите кнопку **Справка**.</span><span class="sxs-lookup"><span data-stu-id="c0e9b-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c0e9b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c0e9b-116">See also</span></span>

[<span data-ttu-id="c0e9b-117">Связь хранилища мониторинга с интерфейсным пулом в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="c0e9b-117">Associate a monitoring store with a Front End pool in Skype for Business Server 2015</span></span>](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)