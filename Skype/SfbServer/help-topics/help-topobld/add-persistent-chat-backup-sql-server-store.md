---
title: Добавление резервного хранилища SQL Server сохраняемого чата
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: Настроить резервные хранилища SQL Server резервных копий, которые будут предоставлять резервные базы данных для сервера сохраняемой беседы или пула серверов сохраняемой беседы.
ms.openlocfilehash: c21cd099372bb49b621447697320df2785a0c9dc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818739"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a><span data-ttu-id="1c26c-103">Добавление резервного хранилища SQL Server сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="1c26c-103">Add Persistent Chat Backup SQL Server Store</span></span>
 
<span data-ttu-id="1c26c-104">Настроить резервные хранилища SQL Server резервных копий, которые будут предоставлять резервные базы данных для сервера сохраняемой беседы или пула серверов сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="1c26c-104">You configure the Backup SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="1c26c-105">**SQL Server хранения:** выберите существующий SQL Server и при желании экземпляр для сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="1c26c-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="1c26c-106">Щелкните **"Новое",** чтобы определить новый SQL Server и при желании новый экземпляр для данных резервного копирования сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="1c26c-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="1c26c-107">Чтобы настроить **базу SQL Server** и необязательный экземпляр, который будет предоставлять зеркальную базу данных для данных резервного копирования сохраняемой беседы, выберите SQL Server для хранения данных зеркального хранения.</span><span class="sxs-lookup"><span data-stu-id="1c26c-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="1c26c-108">Выберите в списке зеркальное **SQL Server** сохранить SQL Server и необязательный экземпляр для SQL Server для резервного копирования сохраняемой беседы SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1c26c-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup SQL Server.</span></span>
  
<span data-ttu-id="1c26c-109">Щелкните **"Новое",** чтобы определить новый SQL Server и при желании новый экземпляр для зеркального SQL Server сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="1c26c-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="1c26c-110">Выберите в списке **Использовать свидетель зеркалирования SQL Server для автоматического перехода на другой ресурс** сервер SQL Server, который будет выступать в качестве следящего сервера в сценариях отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="1c26c-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="1c26c-111">Сервер-свидетель не зеркально и не служит для хранения данных для серверов сохраняемой беседы, но гарантирует, что только SQL Server в зеркальной конфигурации является активным SQL Server в любое время.</span><span class="sxs-lookup"><span data-stu-id="1c26c-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="1c26c-112">Нажмите **кнопку** "Новое", чтобы определить новый SQL Server,при желании экземпляр резервного SQL Server сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="1c26c-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="1c26c-113">Нажмите кнопку **Назад**, чтобы вернуться в предыдущее диалоговое окно определения пула.</span><span class="sxs-lookup"><span data-stu-id="1c26c-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="1c26c-114">Нажмите **кнопку** "Далее", когда закончите вводить параметры для конфигурации резервного SQL Server пула пула и переходить к определению пула серверов сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="1c26c-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="1c26c-115">Нажмите кнопку **Отмена**, чтобы отменить все изменения и завершить работу с мастером **Определение нового пула сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="1c26c-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="1c26c-116">Нажмите кнопку **Справка**, чтобы открыть контекстно-зависимую справку, аналогичную данной странице.</span><span class="sxs-lookup"><span data-stu-id="1c26c-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1c26c-117">См. также</span><span class="sxs-lookup"><span data-stu-id="1c26c-117">See also</span></span>

[<span data-ttu-id="1c26c-118">Планирование сервера сохраняемой беседы в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="1c26c-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="1c26c-119">Требования к серверу для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="1c26c-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="1c26c-120">Требования к оборудованию и программному обеспечению для сервера сохраняемой беседы в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="1c26c-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="1c26c-121">Настройка высокой доступности и аварийного восстановления для сервера сохраняемой беседы в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="1c26c-121">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
