---
title: Добавление резервного хранилища SQL Server сохраняемого чата
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: Следует настроить резервные хранилища SQL Server, предоставляющие резервные базы данных для сервера сохраняемого чата или пул серверов сохраняемого чата.
ms.openlocfilehash: feb4b212c24bc6764dc35f3b4f238be655d50c7e
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2018
---
# <a name="add-persistent-chat-backup-sql-server-store"></a><span data-ttu-id="b6f6c-103">Добавление резервного хранилища SQL Server сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="b6f6c-103">Add Persistent Chat Backup SQL Server Store</span></span>
 
<span data-ttu-id="b6f6c-104">Следует настроить резервные хранилища SQL Server, предоставляющие резервные базы данных для сервера сохраняемого чата или пул серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="b6f6c-104">You configure the Backup SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="b6f6c-105">**Хранилища SQL Server**: выберите существующий SQL Server и при необходимости экземпляр для сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="b6f6c-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="b6f6c-106">Нажмите кнопку **Создать** , чтобы определить новый SQL Server и при необходимости новый экземпляр для данных резервного копирования сохраняемого сеанса беседы.</span><span class="sxs-lookup"><span data-stu-id="b6f6c-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="b6f6c-107">Установите флажок **зеркальное отображение хранилища SQL Server для включения** для настройки базы данных SQL Server и дополнительного экземпляра, который будет предоставлять зеркальной базы данных для резервного копирования данных Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="b6f6c-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="b6f6c-108">Выберите в списке **зеркалирование хранилища SQL Server** SQL Server и необязательный экземпляр для использования в качестве зеркала SQL Server для SQL Server Persistent Chat резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="b6f6c-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup SQL Server.</span></span>
  
<span data-ttu-id="b6f6c-109">Нажмите кнопку **Создать** , чтобы определить новый SQL Server и при необходимости и новый экземпляр для зеркального отображения сохраняемого сеанса беседы SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b6f6c-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="b6f6c-110">В списке **Использовать свидетель зеркалирования SQL Server для автоматического перехода на другой ресурс** выберите сервер SQL Server, который будет служить следящим сервером в ситуациях отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="b6f6c-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="b6f6c-111">Следящий сервер не не зеркала или ведущего приложения данные для серверов сохраняемых сеансов беседы, но гарантирует, что только один сервер SQL в зеркальной конфигурации active SQL Server в любое время.</span><span class="sxs-lookup"><span data-stu-id="b6f6c-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="b6f6c-112">Нажмите кнопку **Создать** , чтобы определить новый свидетель SQL Server, а при необходимости экземпляр для сохраняемого сеанса беседы резервного копирования SQL Server следящий сервер зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="b6f6c-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="b6f6c-113">Для возврата к предыдущему диалоговому окну определения пула нажмите кнопку **Назад**.</span><span class="sxs-lookup"><span data-stu-id="b6f6c-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="b6f6c-114">После завершения ввода значений для этого пула резервной копии конфигурации хранилища сервера SQL Server, чтобы продолжить определение пула серверов сохраняемого чата нажмите кнопку **Далее** .</span><span class="sxs-lookup"><span data-stu-id="b6f6c-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="b6f6c-115">Для отмены всех изменений нажмите кнопку **Отмена**; при этом работа с мастером **Определение нового пула сохраняемого чата** завершается.</span><span class="sxs-lookup"><span data-stu-id="b6f6c-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="b6f6c-116">Для доступа к контекстно-зависимой справке, аналогичной данной странице, нажмите кнопку **Справка**.</span><span class="sxs-lookup"><span data-stu-id="b6f6c-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b6f6c-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b6f6c-117">See also</span></span>

#### 

[<span data-ttu-id="b6f6c-118">Планирование для сервера сохраняемого чата в Скайп Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b6f6c-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="b6f6c-119">Требования к серверу для Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b6f6c-119">Server requirements for Skype for Business Server 2015</span></span>](../../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="b6f6c-120">Аппаратные и программные требования для сервера сохраняемого чата в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b6f6c-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="b6f6c-121">Настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b6f6c-121">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

