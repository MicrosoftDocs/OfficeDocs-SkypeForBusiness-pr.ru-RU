---
title: Добавление резервного хранилища SQL Server соответствия сохраняемого чата
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
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Необходимо настроить резервные хранилища соответствия SQL Server, которые будут предоставлять резервные базы данных для серверов сохраняемой беседы или SQL Server сохраняемой беседы.
ms.openlocfilehash: 9b380091978d62294c6ea16ffa8586b9f8d9d322
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818719"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a><span data-ttu-id="ebbc0-103">Добавление резервного хранилища SQL Server соответствия сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="ebbc0-103">Add Persistent Chat Compliance Backup SQL Server Store</span></span>
 
<span data-ttu-id="ebbc0-104">Необходимо настроить резервные хранилища соответствия SQL Server, которые будут предоставлять резервные базы данных для серверов сохраняемой беседы или SQL Server сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="ebbc0-104">You configure the Backup compliance SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server compliance SQL Server stores.</span></span>
  
 <span data-ttu-id="ebbc0-105">**SQL Server хранения:** выберите существующий SQL Server и при желании экземпляр для сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="ebbc0-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="ebbc0-106">Щелкните **"Новое",** чтобы определить новый SQL Server и при желании новый экземпляр для данных соответствия для резервного копирования сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="ebbc0-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="ebbc0-107">Чтобы настроить **базу данных** SQL Server и необязательный экземпляр, который будет предоставлять зеркальную базу данных для данных соответствия сохраняемой беседы, выберите SQL Server для хранения данных о зеркальном отображке.</span><span class="sxs-lookup"><span data-stu-id="ebbc0-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="ebbc0-108">Выберите в списке зеркальное **SQL Server** сохранить SQL Server и необязательный экземпляр, чтобы выступать в качестве зеркала SQL Server для резервного копирования сохраняемой беседы SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ebbc0-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup compliance SQL Server.</span></span>
  
<span data-ttu-id="ebbc0-109">Щелкните **"Новое",** чтобы определить новый SQL Server и при желании новый экземпляр для зеркального SQL Server сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="ebbc0-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="ebbc0-110">Выберите в списке **Использовать свидетель зеркалирования SQL Server для автоматического перехода на другой ресурс** сервер SQL Server, который будет выступать в качестве следящего сервера в сценариях отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="ebbc0-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="ebbc0-111">На сервере-свидетеле не зеркально отражаются данные серверов сохраняемой беседы и не SQL Server только один сервер в зеркальной конфигурации является активным SQL Server в любое время.</span><span class="sxs-lookup"><span data-stu-id="ebbc0-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="ebbc0-112">Нажмите **кнопку** "Новое", чтобы определить новый SQL Server-свидетель, при желании экземпляр для резервного копирования данных соответствия для сохраняемой беседы SQL Server-свидетеля зеркального зеркального отражания.</span><span class="sxs-lookup"><span data-stu-id="ebbc0-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="ebbc0-113">Нажмите кнопку **Назад**, чтобы вернуться в предыдущее диалоговое окно определения пула.</span><span class="sxs-lookup"><span data-stu-id="ebbc0-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="ebbc0-114">Нажмите **кнопку** "Далее", когда закончите ввод параметров резервной копии этого пула SQL Server конфигурации и перейдите к определению пула сервера сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="ebbc0-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="ebbc0-115">Нажмите кнопку **Отмена**, чтобы отменить все изменения и завершить работу с мастером **Определение нового пула сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="ebbc0-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="ebbc0-116">Нажмите кнопку **Справка**, чтобы открыть контекстно-зависимую справку, аналогичную данной странице.</span><span class="sxs-lookup"><span data-stu-id="ebbc0-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ebbc0-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ebbc0-117">See also</span></span>

[<span data-ttu-id="ebbc0-118">Планирование сервера сохраняемой беседы в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="ebbc0-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="ebbc0-119">Требования к серверу для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="ebbc0-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="ebbc0-120">Требования к оборудованию и программному обеспечению для сервера сохраняемой беседы в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="ebbc0-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="ebbc0-121">Настройка службы соответствия для сервера сохраняемой беседы в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="ebbc0-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)
  
[<span data-ttu-id="ebbc0-122">Настройка высокой доступности и аварийного восстановления для сервера сохраняемой беседы в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="ebbc0-122">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
