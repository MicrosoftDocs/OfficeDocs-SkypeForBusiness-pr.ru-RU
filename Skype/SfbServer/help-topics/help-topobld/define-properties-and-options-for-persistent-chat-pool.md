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
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Вы можете настроить параметры сервера сохраняемого чата или пула серверов сохраняемого чата, определив следующие свойства:'
ms.openlocfilehash: 8d3cef04d7089ffff640740bb048ca52cf7fd91e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218550"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="9f983-103">Определение свойств и параметров для пула сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="9f983-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="9f983-104">Вы можете настроить параметры сервера сохраняемого чата или пула серверов сохраняемого чата, определив следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="9f983-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="9f983-105">**Отображаемое имя пула сохраняемого чата**: обязательное свойство, которое определяет понятное имя пользователя, которое будет отображаться для этого сервера сохраняемого чата или пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="9f983-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="9f983-106">**Порт сохраняемого чата**: обязательное свойство, которое определяет номер порта, который будет прослушивать этот сервер сохраняемого чата или пул серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="9f983-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="9f983-107">**Включить соответствие**: Установите этот флажок, если планируется развертывание и реализация дополнительной функции обеспечения соответствия сохраняемого чата и базы данных.</span><span class="sxs-lookup"><span data-stu-id="9f983-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="9f983-108">**Используйте резервное копирование хранилищ SQL Server для включения аварийного восстановления**: Установите этот флажок, если планируется развертывание и реализация аварийного восстановления хранилищ SQL Server сохраняемого чата из настроенного резервного набора хранилищ на другом сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9f983-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="9f983-109">Дополнительные сведения: [Настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Skype для бизнеса server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="9f983-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9f983-110">Этот параметр доступен только для пулов из нескольких серверов.</span><span class="sxs-lookup"><span data-stu-id="9f983-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="9f983-111">\*\*Использовать этот пул по умолчанию для сайта \<site that this server or pool is being configured in\> \*\*: Установите этот флажок, если это будет сервер сохраняемого чата по умолчанию или пул серверов сохраняемого чата для сайта.</span><span class="sxs-lookup"><span data-stu-id="9f983-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="9f983-112">Для каждого сайта должен быть установлен один сервер сохраняемого чата по умолчанию или POL.</span><span class="sxs-lookup"><span data-stu-id="9f983-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9f983-113">Если топология включает несколько сайтов, также отображается флажок **Использовать пул по умолчанию для всех сайтов**.</span><span class="sxs-lookup"><span data-stu-id="9f983-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="9f983-114">Нажмите кнопку **Назад**, чтобы вернуться в предыдущее диалоговое окно определения пула.</span><span class="sxs-lookup"><span data-stu-id="9f983-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="9f983-115">После завершения ввода параметров для этого пула нажмите кнопку **Далее** , чтобы продолжить определение пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="9f983-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="9f983-116">Нажмите кнопку **Отмена**, чтобы отменить все изменения и завершить работу с мастером **Определение нового пула сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="9f983-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="9f983-117">Нажмите кнопку **Справка**, чтобы открыть контекстно-зависимую справку, аналогичную данной странице.</span><span class="sxs-lookup"><span data-stu-id="9f983-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9f983-118">См. также</span><span class="sxs-lookup"><span data-stu-id="9f983-118">See also</span></span>

[<span data-ttu-id="9f983-119">Планирование сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="9f983-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="9f983-120">Добавление сервера сохраняемого чата к топологии Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="9f983-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
