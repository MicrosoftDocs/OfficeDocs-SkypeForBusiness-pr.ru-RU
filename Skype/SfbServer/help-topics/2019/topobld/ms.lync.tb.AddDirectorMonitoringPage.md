---
title: Добавление мониторинга директора
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorMonitoringPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a9009434-3771-475f-8314-c104f2716a29
ROBOTS: NOINDEX, NOFOLLOW
description: 'Вы можете определить хранилище SQL Server для мониторинга, настроив следующие свойства:'
ms.openlocfilehash: dd6381588580bb5761fdc727630b58d115921d9d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305183"
---
# <a name="add-director-monitoring"></a><span data-ttu-id="4fd94-103">Добавление мониторинга директора</span><span class="sxs-lookup"><span data-stu-id="4fd94-103">Add Director Monitoring</span></span>
 
<span data-ttu-id="4fd94-104">Вы можете **определить хранилище SQL Server для мониторинга** , настроив следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="4fd94-104">You can **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="4fd94-105">**Наблюдение за хранилищем SQL Server**: выберите в списке полное доменное имя SQL Server (FQDN) (и, при необходимости, имя экземпляра SQL Server).</span><span class="sxs-lookup"><span data-stu-id="4fd94-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (FQDN) (and, optionally, a named SQL Server instance) from the list.</span></span>
    
    <span data-ttu-id="4fd94-106">Нажмите кнопку **создать** , чтобы создать новое определение полного доменного имени SQL Server и (необязательно) имя экземпляра для хранилища серверов мониторинга.</span><span class="sxs-lookup"><span data-stu-id="4fd94-106">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="4fd94-107">Установите флажок **включить зеркальное отображение хранилища SQL Server** , если вы хотите добавить зеркальное отображение базы данных для сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="4fd94-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="4fd94-108">Выберите существующее **зеркало хранилища SQL Server для мониторинга** из списка.</span><span class="sxs-lookup"><span data-stu-id="4fd94-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="4fd94-109">Нажмите кнопку **создать** , чтобы создать новое определение полного доменного имени SQL Server и (необязательно) имя экземпляра для зеркального хранилища.</span><span class="sxs-lookup"><span data-stu-id="4fd94-109">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="4fd94-110">Если вы выбрали **включить зеркальное отображение хранилища SQL Server**, при необходимости установите флажок **использовать следящий сервер SQL Server, чтобы включить автоматический переход на другой ресурс** , чтобы выбрать в списке хранилище СВИДЕТЕЛЯ зеркального отображения SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4fd94-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="4fd94-111">Нажмите кнопку **создать** , чтобы создать новое определение полного доменного имени SQL Server и (необязательно) имя экземпляра для хранилища следящего сервера зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="4fd94-111">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="4fd94-112">Для возврата к предыдущему диалоговому окну определения пула нажмите кнопку **Назад**.</span><span class="sxs-lookup"><span data-stu-id="4fd94-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="4fd94-113">После того как вы закончите ввод параметров для этого диалогового окна, нажмите кнопку **Далее** , чтобы продолжить настройку.</span><span class="sxs-lookup"><span data-stu-id="4fd94-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="4fd94-114">Нажмите кнопку **Отмена** , чтобы отменить все изменения и завершить работу мастера.</span><span class="sxs-lookup"><span data-stu-id="4fd94-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="4fd94-115">Выберите команду **Справка** , чтобы получить контекстно-зависимую справку, например на этой странице.</span><span class="sxs-lookup"><span data-stu-id="4fd94-115">Click **Help** to access context-sensitive help, such as this page.</span></span>
  

