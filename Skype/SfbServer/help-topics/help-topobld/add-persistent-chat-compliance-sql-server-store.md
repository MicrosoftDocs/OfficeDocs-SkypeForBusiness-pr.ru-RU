---
title: Добавление хранилища SQL Server для совместимости сохраняемого чата
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: Вы настраиваете хранилища соответствия SQL Server, которые будут предоставлять базы данных для сервера сохраняемого чата или функции соответствия сервера сохраняемого чата.
ms.openlocfilehash: 748fe7a0798bc8e10d3d10832763d5c3e1f55648
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218690"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a><span data-ttu-id="81a64-103">Добавление хранилища SQL Server для совместимости сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="81a64-103">Add Persistent Chat Compliance SQL Server Store</span></span>
 
<span data-ttu-id="81a64-104">Вы настраиваете хранилища соответствия SQL Server, которые будут предоставлять базы данных для сервера сохраняемого чата или функции соответствия сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="81a64-104">You configure the compliance SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server compliance feature.</span></span>
  
 <span data-ttu-id="81a64-105">**Хранилище SQL Server**: выберите существующий SQL Server и, при необходимости, экземпляр сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="81a64-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="81a64-106">Нажмите кнопку **создать** , чтобы определить новый SQL Server и, при необходимости, новый экземпляр для данных соответствия сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="81a64-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat compliance data.</span></span>
  
<span data-ttu-id="81a64-107">Установите флажок **включить зеркалирование хранилища SQL Server** , чтобы настроить базу данных SQL Server и Необязательный экземпляр, который будет предоставлять зеркальную базу данных для данных соответствия сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="81a64-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat compliance data.</span></span>
  
<span data-ttu-id="81a64-108">Выберите в списке **зеркальное отображение хранилища SQL** Server, а затем — SQL Server и Необязательный экземпляр, который будет служить зеркалом SQL Server для обеспечения соответствия сохраняемого чата для SQL Server.</span><span class="sxs-lookup"><span data-stu-id="81a64-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat compliance SQL Server.</span></span>
  
<span data-ttu-id="81a64-109">Нажмите кнопку **создать** , чтобы определить новый SQL Server и, при необходимости, новый экземпляр для зеркального отображения SQL Server сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="81a64-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="81a64-110">Выберите в списке **Использовать свидетель зеркалирования SQL Server для автоматического перехода на другой ресурс** сервер SQL Server, который будет выступать в качестве следящего сервера в сценариях отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="81a64-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="81a64-111">Следящий сервер не выполняет зеркальное отображение и размещение данных для серверов сохраняемого чата, но гарантирует, что в любой момент времени только один SQL Server в зеркальной конфигурации является активным сервером SQL Server.</span><span class="sxs-lookup"><span data-stu-id="81a64-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="81a64-112">Нажмите кнопку **создать** , чтобы определить новый следящий сервер SQL Server, а также экземпляр для свидетеля зеркального отображения зеркального отображения SQL Server для сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="81a64-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="81a64-113">Нажмите кнопку **Назад**, чтобы вернуться в предыдущее диалоговое окно определения пула.</span><span class="sxs-lookup"><span data-stu-id="81a64-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="81a64-114">После завершения ввода параметров для конфигурации хранилища SQL Server для этого пула нажмите кнопку **Далее** , чтобы перейти к определению пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="81a64-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="81a64-115">Нажмите кнопку **Отмена**, чтобы отменить все изменения и завершить работу с мастером **Определение нового пула сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="81a64-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="81a64-116">Нажмите кнопку **Справка**, чтобы открыть контекстно-зависимую справку, аналогичную данной странице.</span><span class="sxs-lookup"><span data-stu-id="81a64-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="81a64-117">См. также</span><span class="sxs-lookup"><span data-stu-id="81a64-117">See also</span></span>

[<span data-ttu-id="81a64-118">Планирование сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="81a64-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="81a64-119">Требования к серверу для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="81a64-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="81a64-120">Требования к оборудованию и программному обеспечению для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="81a64-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="81a64-121">Настройка службы соответствия для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="81a64-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)
