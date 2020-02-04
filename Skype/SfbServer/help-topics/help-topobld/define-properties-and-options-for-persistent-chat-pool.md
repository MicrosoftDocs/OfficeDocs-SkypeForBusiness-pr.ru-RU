---
title: Определение свойств и параметров для пула сохраняемого чата
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: Вы можете настроить параметры почтового сервера или пула сохраняемого чата, определив указанные ниже свойства.
ms.openlocfilehash: 458e50ecc3ddd389a8e413e8f2dd368fc0f15369
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697554"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="b721f-103">Определение свойств и параметров для пула сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="b721f-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="b721f-104">Вы можете настроить параметры почтового сервера или пула сохраняемого чата, определив указанные ниже свойства.</span><span class="sxs-lookup"><span data-stu-id="b721f-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="b721f-105">**Отображаемое имя пула сохраняемого чата**: обязательное свойство, которое определяет понятное имя, которое будет отображаться для этого сохраняемого сервера чатов или для пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="b721f-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="b721f-106">**Постоянный порт чата**: обязательное свойство, определяющее номер порта, который будет прослушивать этот сервер сохраняемого чата или пул серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="b721f-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="b721f-107">**Включить соответствие**: установите флажок, если вы планируете развернуть и внедрить дополнительную функцию соответствия средств и базу данных.</span><span class="sxs-lookup"><span data-stu-id="b721f-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="b721f-108">**Использование резервного копирования хранилищ SQL Server для включения аварийного восстановления**: Установите этот флажок, если вы планируете развертывание и внедрение аварийного восстановления сохраняемого сервера SQL Server хранилища из настроенного резервного набора хранилищ на другом сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b721f-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="b721f-109">Подробнее: [Настройка высокой доступности и аварийного восстановления для постоянного сервера чата в Skype для бизнеса Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="b721f-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b721f-110">Этот параметр доступен только для пулов из нескольких серверов.</span><span class="sxs-lookup"><span data-stu-id="b721f-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="b721f-111">**Использовать этот пул по умолчанию для сайта \<сайта, на\>котором настроен этот сервер или пул**: Установите этот флажок, если он будет использоваться по умолчанию (сохраняемый сервер или пул сохраняемого чата-сервера для сайта).</span><span class="sxs-lookup"><span data-stu-id="b721f-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="b721f-112">У вас должен быть один сервер или разговаривать по умолчанию для каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="b721f-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b721f-113">Если топология содержит несколько сайтов, отображается также флажок **Использовать пул по умолчанию для всех сайтов**.</span><span class="sxs-lookup"><span data-stu-id="b721f-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="b721f-114">Для возврата к предыдущему диалоговому окну определения пула нажмите кнопку **Назад**.</span><span class="sxs-lookup"><span data-stu-id="b721f-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="b721f-115">После того как вы закончите ввод параметров для этого пула, нажмите кнопку **Далее** , чтобы перейти к определению пула сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="b721f-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="b721f-116">Для отмены всех изменений нажмите кнопку **Отмена**; при этом работа с мастером **Определение нового пула сохраняемого чата** завершается.</span><span class="sxs-lookup"><span data-stu-id="b721f-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="b721f-117">Для доступа к контекстно-зависимой справке, аналогичной данной странице, нажмите кнопку **Справка**.</span><span class="sxs-lookup"><span data-stu-id="b721f-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b721f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b721f-118">See also</span></span>

[<span data-ttu-id="b721f-119">Планирование для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="b721f-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="b721f-120">Добавление постоянного сервера чата в топологию 2015 в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b721f-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
