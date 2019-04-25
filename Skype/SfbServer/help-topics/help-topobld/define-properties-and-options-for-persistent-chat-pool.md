---
title: Определение свойств и параметров для пула сохраняемого чата
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Чтобы настроить параметры сервера сохраняемого чата или пул серверов сохраняемого чата, определив следующие свойства:'
ms.openlocfilehash: 380a1e34e041368d4520cd5c8ecea5b18284ef51
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226923"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="20bd2-103">Определение свойств и параметров для пула сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="20bd2-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="20bd2-104">Чтобы настроить параметры сервера сохраняемого чата или пул серверов сохраняемого чата, определив следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="20bd2-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="20bd2-105">**Отображаемое имя пула Persistent Chat**: обязательное свойство, которое определяет понятное имя, которое будет отображаться для этого сервера сохраняемого чата или пул серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="20bd2-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="20bd2-106">**Сохраняемый чат порт**: обязательное свойство, которое определяет порт, какой номер, который в этом сервера сохраняемого чата или прослушивания пул серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="20bd2-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="20bd2-107">**Соответствие требованиям**: установите флажок, если вы планируете развернуть и реализовать дополнительные функции соответствия Persistent Chat и базы данных.</span><span class="sxs-lookup"><span data-stu-id="20bd2-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="20bd2-108">**Использовать резервные хранилища SQL Server возможность аварийного восстановления**: Установите этот флажок, если вы планируете развернуть и реализовать аварийного восстановления для сохраняемого сеанса беседы SQL Server хранит из настроенного набора резервных данных хранилища на другой сервер SQL.</span><span class="sxs-lookup"><span data-stu-id="20bd2-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="20bd2-109">Дополнительные сведения см [Настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Скайп для Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="20bd2-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="20bd2-110">Этот параметр доступен только для пулов из нескольких серверов.</span><span class="sxs-lookup"><span data-stu-id="20bd2-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="20bd2-111">**Использовать этот пул по умолчанию для сайта \<сайт, который этого сервера или пула настраивается в\>**: Установите этот флажок, если это будет по умолчанию сервера сохраняемого чата или пул серверов сохраняемого чата для сайта.</span><span class="sxs-lookup"><span data-stu-id="20bd2-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="20bd2-112">Необходимо иметь один сервер сохраняемых сеансов беседы по умолчанию или pol каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="20bd2-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="20bd2-113">Если топология содержит несколько сайтов, отображается также флажок **Использовать пул по умолчанию для всех сайтов**.</span><span class="sxs-lookup"><span data-stu-id="20bd2-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="20bd2-114">Для возврата к предыдущему диалоговому окну определения пула нажмите кнопку **Назад**.</span><span class="sxs-lookup"><span data-stu-id="20bd2-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="20bd2-115">После завершения ввода значений для этого пула перейти к определению пула серверов сохраняемого чата нажмите кнопку **Далее** .</span><span class="sxs-lookup"><span data-stu-id="20bd2-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="20bd2-116">Для отмены всех изменений нажмите кнопку **Отмена**; при этом работа с мастером **Определение нового пула сохраняемого чата** завершается.</span><span class="sxs-lookup"><span data-stu-id="20bd2-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="20bd2-117">Для доступа к контекстно-зависимой справке, аналогичной данной странице, нажмите кнопку **Справка**.</span><span class="sxs-lookup"><span data-stu-id="20bd2-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="20bd2-118">См. также</span><span class="sxs-lookup"><span data-stu-id="20bd2-118">See also</span></span>

[<span data-ttu-id="20bd2-119">Планирование для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="20bd2-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="20bd2-120">Добавление сервера сохраняемого чата для вашей Скайп для топологии Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="20bd2-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
