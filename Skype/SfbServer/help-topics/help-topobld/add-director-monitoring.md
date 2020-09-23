---
title: Добавление мониторинга Директора
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
- ms.lync.tb.AddDirectorMonitoringPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a9009434-3771-475f-8314-c104f2716a29
description: 'Вы можете выполнить Определение хранилища SQL Server для мониторинга, настроив следующие свойства:'
ms.openlocfilehash: 48a626483da0dd69f46eca9740b0a9b224218f4d
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215500"
---
# <a name="add-director-monitoring"></a><span data-ttu-id="b3d1c-103">Добавление мониторинга Директора</span><span class="sxs-lookup"><span data-stu-id="b3d1c-103">Add Director Monitoring</span></span>
 
<span data-ttu-id="b3d1c-104">Вы можете выполнить **Определение хранилища SQL Server для мониторинга**, настроив следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="b3d1c-104">You can **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="b3d1c-105">**Мониторинг хранилища SQL Server**: выберите в списке полное доменное имя SQL Server (и, при необходимости, именованный экземпляр SQL Server).</span><span class="sxs-lookup"><span data-stu-id="b3d1c-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (FQDN) (and, optionally, a named SQL Server instance) from the list.</span></span>
    
    <span data-ttu-id="b3d1c-106">Нажмите кнопку **создать** , чтобы создать новое определение полного доменного имени SQL Server и (необязательно) имя экземпляра для хранилища сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="b3d1c-106">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="b3d1c-107">Установите флажок **включить зеркалирование хранилища SQL Server** , если необходимо добавить зеркальное отображение базы данных для сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="b3d1c-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="b3d1c-108">Выберите в списке существующее **Зеркало хранилища данных наблюдения SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="b3d1c-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="b3d1c-109">Нажмите кнопку **создать** , чтобы создать новое определение полного доменного имени SQL Server и (необязательно) имя экземпляра для зеркального хранилища.</span><span class="sxs-lookup"><span data-stu-id="b3d1c-109">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="b3d1c-110">Если вы выбрали **включить зеркальное отображение хранилища SQL Server**, при необходимости выберите **использовать следящий сервер ЗЕРКАЛЬного отображения SQL Server для включения автоматического перехода на другой ресурс** , чтобы выбрать в списке резервное хранилище SQL Server для зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="b3d1c-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="b3d1c-111">Нажмите кнопку **создать** , чтобы создать новое определение полного доменного имени SQL Server и (необязательно) имя экземпляра для хранилища-свидетеля зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="b3d1c-111">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="b3d1c-112">Нажмите кнопку **Назад**, чтобы вернуться в предыдущее диалоговое окно определения пула.</span><span class="sxs-lookup"><span data-stu-id="b3d1c-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="b3d1c-113">После завершения ввода значений в этом диалоговом окне нажмите кнопку **Далее**, чтобы продолжить настройку.</span><span class="sxs-lookup"><span data-stu-id="b3d1c-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="b3d1c-114">Нажмите кнопку **Отмена**, чтобы отменить все изменения и завершить работу мастера.</span><span class="sxs-lookup"><span data-stu-id="b3d1c-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="b3d1c-115">Нажмите кнопку **Справка**, чтобы открыть контекстно-зависимую справку, аналогичную данной странице.</span><span class="sxs-lookup"><span data-stu-id="b3d1c-115">Click **Help** to access context-sensitive help, such as this page.</span></span>
  

