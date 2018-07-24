---
title: Добавление мониторинга директора
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorMonitoringPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a9009434-3771-475f-8314-c104f2716a29
description: 'Можно определить хранилище SQL Server для мониторинга, настроив следующие свойства:'
ms.openlocfilehash: cb246ab0fb6413e5bc47ac2d18a9f568d0571f9d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20973873"
---
# <a name="add-director-monitoring"></a><span data-ttu-id="66dcf-103">Добавление мониторинга директора</span><span class="sxs-lookup"><span data-stu-id="66dcf-103">Add Director Monitoring</span></span>
 
<span data-ttu-id="66dcf-104">**Определение хранилища SQL Server для мониторинга** можно, настроив следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="66dcf-104">You can **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="66dcf-105">**Хранилища мониторинга SQL Server**: выберите в списке SQL Server полное доменное имя (FQDN) (и, при необходимости именованный экземпляр SQL Server).</span><span class="sxs-lookup"><span data-stu-id="66dcf-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (FQDN) (and, optionally, a named SQL Server instance) from the list.</span></span>
    
    <span data-ttu-id="66dcf-106">Нажмите кнопку **Создать** , чтобы создать новое определение полного доменного ИМЕНИ сервера SQL, а также, имя экземпляра для хранилища сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="66dcf-106">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="66dcf-107">Установите флажок **Включить хранилища SQL Server зеркального отображения** , если вы хотите добавить зеркальное отображение базы данных для сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="66dcf-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="66dcf-108">Выберите в списке существующий **зеркального хранилища мониторинга SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="66dcf-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="66dcf-109">Нажмите кнопку **Создать** , чтобы создать новое определение полного доменного ИМЕНИ сервера SQL, а также, имя экземпляра для зеркального хранилища.</span><span class="sxs-lookup"><span data-stu-id="66dcf-109">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="66dcf-110">Если выбрано **зеркальное отображение хранилища SQL Server для включения**, при необходимости установите **следящий сервер для включения автоматического переключения зеркального отображения с помощью SQL Server** для выбора сервера SQL Server зеркальное отображение хранилища-свидетеля из списка.</span><span class="sxs-lookup"><span data-stu-id="66dcf-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="66dcf-111">Нажмите кнопку **Создать** , чтобы создать новое определение полного доменного ИМЕНИ сервера SQL, а также, имя экземпляра для хранилища-свидетеля зеркалирования.</span><span class="sxs-lookup"><span data-stu-id="66dcf-111">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="66dcf-112">Для возврата к предыдущему диалоговому окну определения пула нажмите кнопку **Назад**.</span><span class="sxs-lookup"><span data-stu-id="66dcf-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="66dcf-113">После завершения ввода значений в этом диалоговом окне продолжить настройку, нажмите кнопку **Далее** .</span><span class="sxs-lookup"><span data-stu-id="66dcf-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="66dcf-114">Нажмите кнопку **Отмена** , чтобы отменить все изменения и завершить работу мастера.</span><span class="sxs-lookup"><span data-stu-id="66dcf-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="66dcf-115">Нажмите кнопку **Справка** для доступа к контекстной справки, например на этой странице.</span><span class="sxs-lookup"><span data-stu-id="66dcf-115">Click **Help** to access context-sensitive help, such as this page.</span></span>
  

