---
title: Добавление резервного хранилища SQL Server соответствия сохраняемого чата
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Настройка резервного копирования соответствия требованиям хранилища SQL Server, который будет предоставлять резервных копий баз данных для сервера сохраняемого чата или соответствия сервера сохраняемого чата хранилища SQL Server.
ms.openlocfilehash: 5dd121facf9008cb1698b0b9ee46eb0dbaa76afa
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/21/2018
ms.locfileid: "19987377"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a><span data-ttu-id="fdb8c-103">Добавление резервного хранилища SQL Server соответствия сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="fdb8c-103">Add Persistent Chat Compliance Backup SQL Server Store</span></span>
 
<span data-ttu-id="fdb8c-104">Настройка резервного копирования соответствия требованиям хранилища SQL Server, который будет предоставлять резервных копий баз данных для сервера сохраняемого чата или соответствия сервера сохраняемого чата хранилища SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fdb8c-104">You configure the Backup compliance SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server compliance SQL Server stores.</span></span>
  
 <span data-ttu-id="fdb8c-105">**Хранилища SQL Server**: выберите существующий SQL Server и при необходимости экземпляр для сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="fdb8c-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="fdb8c-106">Нажмите кнопку **Создать** , чтобы определить новый SQL Server и при необходимости новый экземпляр для данных резервного копирования соответствия Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="fdb8c-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="fdb8c-107">Установите флажок **зеркальное отображение хранилища SQL Server для включения** для настройки базы данных SQL Server и дополнительного экземпляра, который будет предоставлять зеркальной базы данных для данных резервного копирования соответствия Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="fdb8c-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="fdb8c-108">Выберите в списке **зеркалирование хранилища SQL Server** SQL Server и необязательный экземпляр для использования в качестве зеркала SQL Server для соответствия Persistent Chat резервного копирования SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fdb8c-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup compliance SQL Server.</span></span>
  
<span data-ttu-id="fdb8c-109">Нажмите кнопку **Создать** , чтобы определить новый SQL Server и при необходимости и новый экземпляр для зеркального отображения сохраняемого сеанса беседы SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fdb8c-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="fdb8c-110">В списке **Использовать свидетель зеркалирования SQL Server для автоматического перехода на другой ресурс** выберите сервер SQL Server, который будет служить следящим сервером в ситуациях отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="fdb8c-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="fdb8c-111">Следящий сервер не не зеркала или ведущего приложения данные для серверов сохраняемых сеансов беседы, но гарантирует, что только один сервер SQL в зеркальной конфигурации active SQL Server в любое время.</span><span class="sxs-lookup"><span data-stu-id="fdb8c-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="fdb8c-112">Нажмите кнопку **Создать** , чтобы определить новый свидетель SQL Server, а при необходимости еще и экземпляр для соответствия Persistent Chat резервного копирования следящий сервер зеркального отображения SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fdb8c-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="fdb8c-113">Для возврата к предыдущему диалоговому окну определения пула нажмите кнопку **Назад**.</span><span class="sxs-lookup"><span data-stu-id="fdb8c-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="fdb8c-114">После завершения ввода значений для этого пула резервной копии конфигурации хранилища сервера SQL Server, чтобы продолжить определение пула серверов сохраняемого чата нажмите кнопку **Далее** .</span><span class="sxs-lookup"><span data-stu-id="fdb8c-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="fdb8c-115">Для отмены всех изменений нажмите кнопку **Отмена**; при этом работа с мастером **Определение нового пула сохраняемого чата** завершается.</span><span class="sxs-lookup"><span data-stu-id="fdb8c-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="fdb8c-116">Для доступа к контекстно-зависимой справке, аналогичной данной странице, нажмите кнопку **Справка**.</span><span class="sxs-lookup"><span data-stu-id="fdb8c-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fdb8c-117">См. также</span><span class="sxs-lookup"><span data-stu-id="fdb8c-117">See also</span></span>

[<span data-ttu-id="fdb8c-118">Планирование для сервера сохраняемого чата в Скайп Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fdb8c-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="fdb8c-119">Требования к серверу для Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fdb8c-119">Server requirements for Skype for Business Server 2015</span></span>](../../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="fdb8c-120">Аппаратные и программные требования для сервера сохраняемого чата в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fdb8c-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="fdb8c-121">Настройка службы соответствия для сервера сохраняемого чата в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fdb8c-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../../manage/persistent-chat/configure-compliance.md)
  
[<span data-ttu-id="fdb8c-122">Настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fdb8c-122">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)