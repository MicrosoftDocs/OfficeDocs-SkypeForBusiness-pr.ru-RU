---
title: Добавление хранилища SQL Server для сохраняемого чата
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Вы можете настроить хранилища SQL Server, в которых будут предоставляться базы данных для сервера сохраняемого чата или для пула серверов сохраняемого чата.
ms.openlocfilehash: 3d6e5464cf435440cc7e7b1b29aa5a22ae2cbb0f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302282"
---
# <a name="add-persistent-chat-sql-server-store"></a><span data-ttu-id="0d0e7-103">Добавление хранилища SQL Server для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="0d0e7-103">Add Persistent Chat SQL Server Store</span></span>
 
<span data-ttu-id="0d0e7-104">Вы можете настроить хранилища SQL Server, в которых будут предоставляться базы данных для сервера сохраняемого чата или для пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="0d0e7-104">You configure the SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="0d0e7-105">**Хранилище SQL Server**: выберите существующий SQL Server и, при необходимости, экземпляр сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="0d0e7-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="0d0e7-106">Нажмите кнопку **создать** , чтобы определить новый SQL Server и, при необходимости, новый экземпляр для сохраняемых данных чата.</span><span class="sxs-lookup"><span data-stu-id="0d0e7-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat data.</span></span>
  
<span data-ttu-id="0d0e7-107">Установите флажок **включить зеркальное отображение хранилища SQL Server** , чтобы настроить базу данных SQL Server и дополнительный экземпляр, который предоставит зеркальную базу данных для сохраняемых данных чата.</span><span class="sxs-lookup"><span data-stu-id="0d0e7-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat data.</span></span>
  
<span data-ttu-id="0d0e7-108">Выберите из списка **зеркальный набор в SQL Server сохраните** сервер SQL Server и дополнительный экземпляр, чтобы он действовал в качестве зеркального сервера SQL Server для СОХРАНЯЕМого SQL-сервера чата.</span><span class="sxs-lookup"><span data-stu-id="0d0e7-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat SQL Server.</span></span>
  
<span data-ttu-id="0d0e7-109">Нажмите кнопку **создать** , чтобы определить новый SQL Server и создать новый экземпляр для сохраняемого зеркального отображения SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0d0e7-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="0d0e7-110">В списке **Использовать свидетель зеркалирования SQL Server для автоматического перехода на другой ресурс** выберите сервер SQL Server, который будет служить следящим сервером в ситуациях отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="0d0e7-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="0d0e7-111">Сервер-свидетель не может зеркально отражать данные для серверов чатов, но гарантирует, что только один SQL Server в зеркальной конфигурации является активным сервером SQL Server в любой момент.</span><span class="sxs-lookup"><span data-stu-id="0d0e7-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="0d0e7-112">Нажмите кнопку " **создать** ", чтобы определить новый свидетель SQL Server, который является экземпляром для следящего сервера зеркального отображения SQL Server для сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="0d0e7-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="0d0e7-113">Для возврата к предыдущему диалоговому окну определения пула нажмите кнопку **Назад**.</span><span class="sxs-lookup"><span data-stu-id="0d0e7-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="0d0e7-114">После того как вы закончите ввод параметров для конфигурации хранилища SQL Server в этом пуле и продолжите работу с определением пула серверов для сохраняемого чата, нажмите кнопку **Далее** .</span><span class="sxs-lookup"><span data-stu-id="0d0e7-114">Click **Next** after you have finished entering the options for this pool's SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="0d0e7-115">Для отмены всех изменений нажмите кнопку **Отмена**; при этом работа с мастером **Определение нового пула сохраняемого чата** завершается.</span><span class="sxs-lookup"><span data-stu-id="0d0e7-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="0d0e7-116">Для доступа к контекстно-зависимой справке, аналогичной данной странице, нажмите кнопку **Справка**.</span><span class="sxs-lookup"><span data-stu-id="0d0e7-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0d0e7-117">См. также</span><span class="sxs-lookup"><span data-stu-id="0d0e7-117">See also</span></span>

[<span data-ttu-id="0d0e7-118">Планирование для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="0d0e7-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="0d0e7-119">Добавление постоянного сервера чата в топологию 2015 в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="0d0e7-119">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="0d0e7-120">Требования к оборудованию и программному обеспечению для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="0d0e7-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="0d0e7-121">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0d0e7-121">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="0d0e7-122">Основы топологии для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="0d0e7-122">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[<span data-ttu-id="0d0e7-123">Настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="0d0e7-123">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
