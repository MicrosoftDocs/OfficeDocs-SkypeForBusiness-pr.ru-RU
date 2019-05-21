---
title: Добавление резервного хранилища SQL Server сохраняемого чата
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: Вы можете настроить резервные хранилища SQL Server, в которых будут храниться резервные копии для сервера сохраняемого чата или для пула серверов сохраняемого чата.
ms.openlocfilehash: 39e5e1ead6ed3cb089545406852de16170d782dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304655"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a><span data-ttu-id="c249e-103">Добавление резервного хранилища SQL Server сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="c249e-103">Add Persistent Chat Backup SQL Server Store</span></span>
 
<span data-ttu-id="c249e-104">Вы можете настроить резервные хранилища SQL Server, в которых будут храниться резервные копии для сервера сохраняемого чата или для пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="c249e-104">You configure the Backup SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="c249e-105">**Хранилище SQL Server**: выберите существующий SQL Server и, при необходимости, экземпляр сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="c249e-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="c249e-106">Нажмите кнопку **создать** , чтобы определить новый SQL Server и создать новый экземпляр для резервных данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="c249e-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="c249e-107">Установите флажок **включить зеркальное отображение хранилища SQL Server** , чтобы настроить базу данных SQL Server и дополнительный экземпляр, который предоставит зеркальную базу данных для сохраняемого резервного копирования чата.</span><span class="sxs-lookup"><span data-stu-id="c249e-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="c249e-108">Выберите в зеркальном отображении списка в **SQL Server сохраните** сервер SQL Server и Необязательный экземпляр, чтобы он действовал для резервного копирования данных сохраняемого чата, как SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c249e-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup SQL Server.</span></span>
  
<span data-ttu-id="c249e-109">Нажмите кнопку **создать** , чтобы определить новый SQL Server и создать новый экземпляр для сохраняемого зеркального отображения SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c249e-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="c249e-110">В списке **Использовать свидетель зеркалирования SQL Server для автоматического перехода на другой ресурс** выберите сервер SQL Server, который будет служить следящим сервером в ситуациях отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="c249e-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="c249e-111">Сервер-свидетель не может зеркально отражать данные для серверов чатов, но гарантирует, что только один SQL Server в зеркальной конфигурации является активным сервером SQL Server в любой момент.</span><span class="sxs-lookup"><span data-stu-id="c249e-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="c249e-112">Нажмите кнопку **создать** , чтобы определить новый следящий сервер SQL Server, а также экземпляр для резервного копирования с помощью SQL Server Mirroring.</span><span class="sxs-lookup"><span data-stu-id="c249e-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="c249e-113">Для возврата к предыдущему диалоговому окну определения пула нажмите кнопку **Назад**.</span><span class="sxs-lookup"><span data-stu-id="c249e-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="c249e-114">После того как вы закончите ввод параметров для резервного копирования в хранилище SQL Server для этого пула, нажмите кнопку **Далее** , чтобы перейти к определению пула сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="c249e-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="c249e-115">Для отмены всех изменений нажмите кнопку **Отмена**; при этом работа с мастером **Определение нового пула сохраняемого чата** завершается.</span><span class="sxs-lookup"><span data-stu-id="c249e-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="c249e-116">Для доступа к контекстно-зависимой справке, аналогичной данной странице, нажмите кнопку **Справка**.</span><span class="sxs-lookup"><span data-stu-id="c249e-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c249e-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c249e-117">See also</span></span>

[<span data-ttu-id="c249e-118">Планирование для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="c249e-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="c249e-119">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c249e-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="c249e-120">Требования к оборудованию и программному обеспечению для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="c249e-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="c249e-121">Настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="c249e-121">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
