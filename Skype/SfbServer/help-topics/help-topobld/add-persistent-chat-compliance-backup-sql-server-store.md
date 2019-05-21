---
title: Добавление резервного хранилища SQL Server соответствия сохраняемого чата
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Вы настраиваете хранилища SQL Server для обеспечения соответствия резервных копий, которые предоставляют резервные базы данных для сервера сохраняемого чата или сохраняемого сервера в соответствии с требованиями SQL Server Stores.
ms.openlocfilehash: 457874f87266453939c75cdef50d30231d8610bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277708"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a><span data-ttu-id="aedd6-103">Добавление резервного хранилища SQL Server соответствия сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="aedd6-103">Add Persistent Chat Compliance Backup SQL Server Store</span></span>
 
<span data-ttu-id="aedd6-104">Вы настраиваете хранилища SQL Server для обеспечения соответствия резервных копий, которые предоставляют резервные базы данных для сервера сохраняемого чата или сохраняемого сервера в соответствии с требованиями SQL Server Stores.</span><span class="sxs-lookup"><span data-stu-id="aedd6-104">You configure the Backup compliance SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server compliance SQL Server stores.</span></span>
  
 <span data-ttu-id="aedd6-105">**Хранилище SQL Server**: выберите существующий SQL Server и, при необходимости, экземпляр сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="aedd6-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="aedd6-106">Нажмите кнопку **создать** , чтобы определить новый SQL Server и (необязательно) новый экземпляр для данных о соответствии требованиям резервного копирования для сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="aedd6-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="aedd6-107">Установите флажок **включить зеркальное отображение хранилища SQL Server** , чтобы настроить базу данных SQL Server и дополнительный экземпляр, который предоставит зеркальную базу данных соответствия требованиям резервного копирования для сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="aedd6-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="aedd6-108">Выберите из списка **зеркальный набор в SQL Server сохраните** сервер SQL Server и Необязательный экземпляр, чтобы он ДЕЙСТВОВАЛ для SQL Server для соответствия требованиям резервного копирования для сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="aedd6-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup compliance SQL Server.</span></span>
  
<span data-ttu-id="aedd6-109">Нажмите кнопку **создать** , чтобы определить новый SQL Server и создать новый экземпляр для сохраняемого зеркального отображения SQL Server.</span><span class="sxs-lookup"><span data-stu-id="aedd6-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="aedd6-110">В списке **Использовать свидетель зеркалирования SQL Server для автоматического перехода на другой ресурс** выберите сервер SQL Server, который будет служить следящим сервером в ситуациях отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="aedd6-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="aedd6-111">Сервер-свидетель не может зеркально отражать данные для серверов чатов, но гарантирует, что только один SQL Server в зеркальной конфигурации является активным сервером SQL Server в любой момент.</span><span class="sxs-lookup"><span data-stu-id="aedd6-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="aedd6-112">Нажмите кнопку **создать** , чтобы определить новый следящий сервер SQL Server, который является экземпляром для функции зеркального резервного копирования SQL Server с подведением для сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="aedd6-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="aedd6-113">Для возврата к предыдущему диалоговому окну определения пула нажмите кнопку **Назад**.</span><span class="sxs-lookup"><span data-stu-id="aedd6-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="aedd6-114">После того как вы закончите ввод параметров для резервного копирования в хранилище SQL Server для этого пула, нажмите кнопку **Далее** , чтобы перейти к определению пула сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="aedd6-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="aedd6-115">Для отмены всех изменений нажмите кнопку **Отмена**; при этом работа с мастером **Определение нового пула сохраняемого чата** завершается.</span><span class="sxs-lookup"><span data-stu-id="aedd6-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="aedd6-116">Для доступа к контекстно-зависимой справке, аналогичной данной странице, нажмите кнопку **Справка**.</span><span class="sxs-lookup"><span data-stu-id="aedd6-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="aedd6-117">См. также</span><span class="sxs-lookup"><span data-stu-id="aedd6-117">See also</span></span>

[<span data-ttu-id="aedd6-118">Планирование для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="aedd6-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="aedd6-119">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="aedd6-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="aedd6-120">Требования к оборудованию и программному обеспечению для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="aedd6-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="aedd6-121">Настройка службы проверки на соответствие для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="aedd6-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)
  
[<span data-ttu-id="aedd6-122">Настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="aedd6-122">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
