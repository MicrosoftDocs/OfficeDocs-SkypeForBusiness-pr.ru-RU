---
title: Добавление хранилища SQL Server для сохраняемого чата
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
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Настраиваются хранилища SQL Server, которые будут предоставлять базы данных для сервера сохраняемой беседы или пула серверов сохраняемой беседы.
ms.openlocfilehash: e93705e0646f1115994a61c936a5c0cb16149dfa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818659"
---
# <a name="add-persistent-chat-sql-server-store"></a><span data-ttu-id="841b0-103">Добавление хранилища SQL Server для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="841b0-103">Add Persistent Chat SQL Server Store</span></span>
 
<span data-ttu-id="841b0-104">Настраиваются хранилища SQL Server, которые будут предоставлять базы данных для сервера сохраняемой беседы или пула серверов сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="841b0-104">You configure the SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="841b0-105">**SQL Server хранения:** выберите существующий SQL Server и при желании экземпляр для сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="841b0-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="841b0-106">Щелкните **"Новое",** чтобы определить новый SQL Server и при желании новый экземпляр для данных сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="841b0-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat data.</span></span>
  
<span data-ttu-id="841b0-107">Чтобы настроить базу данных SQL Server и необязательный экземпляр, который будет предоставлять зеркальную базу данных для **данных** сохраняемой беседы, выберите SQL Server включить зеркальное зеркальное хранение данных.</span><span class="sxs-lookup"><span data-stu-id="841b0-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat data.</span></span>
  
<span data-ttu-id="841b0-108">Выберите в списке зеркальное **SQL Server** сохранить SQL Server и необязательный экземпляр для SQL Server зеркала для сохраняемой беседы SQL Server.</span><span class="sxs-lookup"><span data-stu-id="841b0-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat SQL Server.</span></span>
  
<span data-ttu-id="841b0-109">Щелкните **"Новое",** чтобы определить новый SQL Server и при желании новый экземпляр для зеркального SQL Server сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="841b0-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="841b0-110">Выберите в списке **Использовать свидетель зеркалирования SQL Server для автоматического перехода на другой ресурс** сервер SQL Server, который будет выступать в качестве следящего сервера в сценариях отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="841b0-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="841b0-111">Сервер-свидетель не зеркально и не служит для хранения данных для серверов сохраняемой беседы, но гарантирует, что только SQL Server в зеркальной конфигурации является активным SQL Server в любое время.</span><span class="sxs-lookup"><span data-stu-id="841b0-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="841b0-112">Нажмите **кнопку** "Новое", чтобы определить новый SQL Server,при желании экземпляр для свидетеля SQL Server сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="841b0-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="841b0-113">Нажмите кнопку **Назад**, чтобы вернуться в предыдущее диалоговое окно определения пула.</span><span class="sxs-lookup"><span data-stu-id="841b0-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="841b0-114">Нажмите **кнопку** "Далее", когда закончите ввод параметров конфигурации SQL Server этого пула, и перейдите к определению пула сервера сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="841b0-114">Click **Next** after you have finished entering the options for this pool's SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="841b0-115">Нажмите кнопку **Отмена**, чтобы отменить все изменения и завершить работу с мастером **Определение нового пула сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="841b0-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="841b0-116">Нажмите кнопку **Справка**, чтобы открыть контекстно-зависимую справку, аналогичную данной странице.</span><span class="sxs-lookup"><span data-stu-id="841b0-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="841b0-117">См. также</span><span class="sxs-lookup"><span data-stu-id="841b0-117">See also</span></span>

[<span data-ttu-id="841b0-118">Планирование сервера сохраняемой беседы в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="841b0-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="841b0-119">Добавление сервера сохраняемой беседы в топологию Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="841b0-119">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="841b0-120">Требования к оборудованию и программному обеспечению для сервера сохраняемой беседы в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="841b0-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="841b0-121">Требования к серверу для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="841b0-121">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="841b0-122">Основы топологии для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="841b0-122">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[<span data-ttu-id="841b0-123">Настройка высокой доступности и аварийного восстановления для сервера сохраняемой беседы в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="841b0-123">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
