---
title: Добавление хранилища SQL Server для совместимости сохраняемого чата
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: Настройка хранилища SQL Server соответствия требованиям, который будет предоставлять баз данных для сервера сохраняемого чата или функции соответствия сервера сохраняемого чата.
ms.openlocfilehash: 7854255195e73dcf03ce9027cdd7390c8f4bde54
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a><span data-ttu-id="9fc1c-103">Добавление хранилища SQL Server для совместимости сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="9fc1c-103">Add Persistent Chat Compliance SQL Server Store</span></span>
 
<span data-ttu-id="9fc1c-104">Настройка хранилища SQL Server соответствия требованиям, который будет предоставлять баз данных для сервера сохраняемого чата или функции соответствия сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-104">You configure the compliance SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server compliance feature.</span></span>
  
 <span data-ttu-id="9fc1c-105">**Хранилища SQL Server**: выберите существующий SQL Server и при необходимости экземпляр для сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="9fc1c-106">Нажмите кнопку **Создать** , чтобы определить новый SQL Server и при необходимости и новый экземпляр для данных соответствия Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat compliance data.</span></span>
  
<span data-ttu-id="9fc1c-107">Установите флажок **Включить хранилища SQL Server зеркальное отображение** для настройки базы данных SQL Server и дополнительного экземпляра, который будет предоставлять зеркальной базы данных для данных соответствия Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat compliance data.</span></span>
  
<span data-ttu-id="9fc1c-108">Выберите в списке **зеркалирование хранилища SQL Server** SQL Server и необязательный экземпляр для использования в качестве зеркала SQL Server для соответствия Persistent Chat SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat compliance SQL Server.</span></span>
  
<span data-ttu-id="9fc1c-109">Нажмите кнопку **Создать** , чтобы определить новый SQL Server и при необходимости и новый экземпляр для зеркального отображения сохраняемого сеанса беседы SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="9fc1c-110">В списке **Использовать свидетель зеркалирования SQL Server для автоматического перехода на другой ресурс** выберите сервер SQL Server, который будет служить следящим сервером в ситуациях отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="9fc1c-111">Следящий сервер не не зеркала или ведущего приложения данные для серверов сохраняемых сеансов беседы, но гарантирует, что только один сервер SQL в зеркальной конфигурации active SQL Server в любое время.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="9fc1c-112">Нажмите кнопку **Создать** , чтобы определить новый свидетель SQL Server, а при необходимости еще и экземпляр для соответствия Persistent Chat следящий сервер зеркального отображения SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="9fc1c-113">Для возврата к предыдущему диалоговому окну определения пула нажмите кнопку **Назад**.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="9fc1c-114">После завершения ввода значений для этого пула резервной копии конфигурации хранилища сервера SQL Server, чтобы продолжить определение пула серверов сохраняемого чата нажмите кнопку **Далее** .</span><span class="sxs-lookup"><span data-stu-id="9fc1c-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="9fc1c-115">Для отмены всех изменений нажмите кнопку **Отмена**; при этом работа с мастером **Определение нового пула сохраняемого чата** завершается.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="9fc1c-116">Для доступа к контекстно-зависимой справке, аналогичной данной странице, нажмите кнопку **Справка**.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9fc1c-117">См. также</span><span class="sxs-lookup"><span data-stu-id="9fc1c-117">See also</span></span>

#### 

[<span data-ttu-id="9fc1c-118">Планирование для сервера сохраняемого чата в Скайп Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9fc1c-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="9fc1c-119">Требования к серверу для Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9fc1c-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="9fc1c-120">Аппаратные и программные требования для сервера сохраняемого чата в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9fc1c-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="9fc1c-121">Настройка службы соответствия для сервера сохраняемого чата в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9fc1c-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)

