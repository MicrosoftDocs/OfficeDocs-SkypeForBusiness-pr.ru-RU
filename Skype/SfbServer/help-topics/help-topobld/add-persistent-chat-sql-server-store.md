---
title: Добавление хранилища SQL Server для сохраняемого чата
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
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Вы настраиваете хранилища SQL Server, которые будут предоставлять базы данных для сервера сохраняемого чата или пула серверов сохраняемого чата.
ms.openlocfilehash: 2771b63063e155973cd711c4b80f06dee46e1865
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216330"
---
# <a name="add-persistent-chat-sql-server-store"></a><span data-ttu-id="fcd3e-103">Добавление хранилища SQL Server для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="fcd3e-103">Add Persistent Chat SQL Server Store</span></span>
 
<span data-ttu-id="fcd3e-104">Вы настраиваете хранилища SQL Server, которые будут предоставлять базы данных для сервера сохраняемого чата или пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="fcd3e-104">You configure the SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="fcd3e-105">**Хранилище SQL Server**: выберите существующий SQL Server и, при необходимости, экземпляр сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="fcd3e-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="fcd3e-106">Нажмите кнопку **создать** , чтобы определить новый SQL Server и, при необходимости, новый экземпляр для данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="fcd3e-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat data.</span></span>
  
<span data-ttu-id="fcd3e-107">Установите флажок **включить зеркалирование хранилища SQL Server** , чтобы настроить базу данных SQL Server и Необязательный экземпляр, который предоставит зеркальную базу данных для данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="fcd3e-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat data.</span></span>
  
<span data-ttu-id="fcd3e-108">Выберите из списка **зеркальное хранилище SQL** Server, а затем SQL Server и Необязательный экземпляр, который будет служить зеркальным сервером SQL Server для сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="fcd3e-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat SQL Server.</span></span>
  
<span data-ttu-id="fcd3e-109">Нажмите кнопку **создать** , чтобы определить новый SQL Server и, при необходимости, новый экземпляр для зеркального отображения SQL Server сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="fcd3e-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="fcd3e-110">Выберите в списке **Использовать свидетель зеркалирования SQL Server для автоматического перехода на другой ресурс** сервер SQL Server, который будет выступать в качестве следящего сервера в сценариях отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="fcd3e-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="fcd3e-111">Следящий сервер не выполняет зеркальное отображение и размещение данных для серверов сохраняемого чата, но гарантирует, что в любой момент времени только один SQL Server в зеркальной конфигурации является активным сервером SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fcd3e-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="fcd3e-112">Нажмите кнопку **создать** , чтобы определить новый следящий сервер SQL Server (при необходимости) для следящего сервера зеркального отображения SQL Server сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="fcd3e-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="fcd3e-113">Нажмите кнопку **Назад**, чтобы вернуться в предыдущее диалоговое окно определения пула.</span><span class="sxs-lookup"><span data-stu-id="fcd3e-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="fcd3e-114">Завершив ввод параметров для конфигурации хранилища SQL Server для этого пула, нажмите кнопку **Далее** , чтобы перейти к определению пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="fcd3e-114">Click **Next** after you have finished entering the options for this pool's SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="fcd3e-115">Нажмите кнопку **Отмена**, чтобы отменить все изменения и завершить работу с мастером **Определение нового пула сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="fcd3e-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="fcd3e-116">Нажмите кнопку **Справка**, чтобы открыть контекстно-зависимую справку, аналогичную данной странице.</span><span class="sxs-lookup"><span data-stu-id="fcd3e-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fcd3e-117">См. также</span><span class="sxs-lookup"><span data-stu-id="fcd3e-117">See also</span></span>

[<span data-ttu-id="fcd3e-118">Планирование сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="fcd3e-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="fcd3e-119">Добавление сервера сохраняемого чата к топологии Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="fcd3e-119">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="fcd3e-120">Требования к оборудованию и программному обеспечению для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="fcd3e-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="fcd3e-121">Требования к серверу для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="fcd3e-121">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="fcd3e-122">Основы топологии для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="fcd3e-122">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[<span data-ttu-id="fcd3e-123">Настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="fcd3e-123">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
