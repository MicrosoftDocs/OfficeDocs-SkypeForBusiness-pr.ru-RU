---
title: Добавление мониторинга директора
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddDirectorMonitoringPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a9009434-3771-475f-8314-c104f2716a29
description: 'Вы можете определить хранилище SQL Server для мониторинга, настроив следующие свойства:'
ms.openlocfilehash: a424cb7ae23688224d52510df5db793b3348a176
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821201"
---
# <a name="add-director-monitoring"></a><span data-ttu-id="dc99a-103">Добавление мониторинга директора</span><span class="sxs-lookup"><span data-stu-id="dc99a-103">Add Director Monitoring</span></span>
 
<span data-ttu-id="dc99a-104">Вы можете **определить хранилище SQL Server для мониторинга** , настроив следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="dc99a-104">You can **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="dc99a-105">**Наблюдение за хранилищем SQL Server**: выберите в списке полное доменное имя SQL Server (FQDN) (и, при необходимости, имя экземпляра SQL Server).</span><span class="sxs-lookup"><span data-stu-id="dc99a-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (FQDN) (and, optionally, a named SQL Server instance) from the list.</span></span>
    
    <span data-ttu-id="dc99a-106">Нажмите кнопку **создать** , чтобы создать новое определение полного доменного имени SQL Server и (необязательно) имя экземпляра для хранилища серверов мониторинга.</span><span class="sxs-lookup"><span data-stu-id="dc99a-106">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="dc99a-107">Установите флажок **включить зеркальное отображение хранилища SQL Server** , если вы хотите добавить зеркальное отображение базы данных для сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="dc99a-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="dc99a-108">Выберите существующее **зеркало хранилища SQL Server для мониторинга** из списка.</span><span class="sxs-lookup"><span data-stu-id="dc99a-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="dc99a-109">Нажмите кнопку **создать** , чтобы создать новое определение полного доменного имени SQL Server и (необязательно) имя экземпляра для зеркального хранилища.</span><span class="sxs-lookup"><span data-stu-id="dc99a-109">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="dc99a-110">Если вы выбрали **включить зеркальное отображение хранилища SQL Server**, при необходимости установите флажок **использовать следящий сервер SQL Server, чтобы включить автоматический переход на другой ресурс** , чтобы выбрать в списке хранилище СВИДЕТЕЛЯ зеркального отображения SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dc99a-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="dc99a-111">Нажмите кнопку **создать** , чтобы создать новое определение полного доменного имени SQL Server и (необязательно) имя экземпляра для хранилища следящего сервера зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="dc99a-111">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="dc99a-112">Для возврата к предыдущему диалоговому окну определения пула нажмите кнопку **Назад**.</span><span class="sxs-lookup"><span data-stu-id="dc99a-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="dc99a-113">После того как вы закончите ввод параметров для этого диалогового окна, нажмите кнопку **Далее** , чтобы продолжить настройку.</span><span class="sxs-lookup"><span data-stu-id="dc99a-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="dc99a-114">Нажмите кнопку **Отмена** , чтобы отменить все изменения и завершить работу мастера.</span><span class="sxs-lookup"><span data-stu-id="dc99a-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="dc99a-115">Выберите команду **Справка** , чтобы получить контекстно-зависимую справку, например на этой странице.</span><span class="sxs-lookup"><span data-stu-id="dc99a-115">Click **Help** to access context-sensitive help, such as this page.</span></span>
  

