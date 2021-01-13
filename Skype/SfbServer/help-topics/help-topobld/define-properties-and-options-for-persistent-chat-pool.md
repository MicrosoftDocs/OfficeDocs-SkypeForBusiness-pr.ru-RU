---
title: Определение свойств и параметров для пула сохраняемого чата
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Параметры сервера сохраняемой беседы или пула серверов сохраняемой беседы настраиваются путем определения следующих свойств:'
ms.openlocfilehash: acc80c76e79364be730ec56a2b64e5dcd001f661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818429"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="31d9c-103">Определение свойств и параметров для пула сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="31d9c-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="31d9c-104">Параметры сервера сохраняемой беседы или пула серверов сохраняемой беседы настраиваются путем определения следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="31d9c-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="31d9c-105">**Отображаемое имя пула** сохраняемого чата : обязательное свойство, которое определяет имя пользователя, которое будет отображаться для этого сервера сохраняемого чата или пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="31d9c-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="31d9c-106">**Порт сохраняемого** чата : обязательное свойство, которое определяет номер порта, который будет прослушиваться этим сервером сохраняемого чата или пулом серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="31d9c-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="31d9c-107">**Включить соответствие** требованиям: если вы планируете развернуть и реализовать дополнительную функцию соответствия сохраняемой беседы и базу данных.</span><span class="sxs-lookup"><span data-stu-id="31d9c-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="31d9c-108">Используйте резервные **хранилища SQL Server** для аварийного восстановления: установите этот контроль, если вы планируете развернуть и реализовать аварийное восстановление хранилищ сохраняемого чата SQL Server из настроенного резервного набора хранилищ на другом SQL Server.</span><span class="sxs-lookup"><span data-stu-id="31d9c-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="31d9c-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="31d9c-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="31d9c-110">Этот параметр доступен только для пулов из нескольких серверов.</span><span class="sxs-lookup"><span data-stu-id="31d9c-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="31d9c-111">**Используйте этот пул по \<site that this server or pool is being configured in\>** умолчанию для сайта: если это будет сервер сохраняемой беседы по умолчанию или пул серверов сохраняемой беседы для сайта.</span><span class="sxs-lookup"><span data-stu-id="31d9c-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="31d9c-112">На сайте должен быть один сервер сохраняемой беседы по умолчанию или pol.</span><span class="sxs-lookup"><span data-stu-id="31d9c-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="31d9c-113">Если топология включает несколько сайтов, также отображается флажок **Использовать пул по умолчанию для всех сайтов**.</span><span class="sxs-lookup"><span data-stu-id="31d9c-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="31d9c-114">Нажмите кнопку **Назад**, чтобы вернуться в предыдущее диалоговое окно определения пула.</span><span class="sxs-lookup"><span data-stu-id="31d9c-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="31d9c-115">Нажмите **кнопку** "Далее", когда закончите ввод параметров для этого пула, чтобы перейти к определению пула сервера сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="31d9c-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="31d9c-116">Нажмите кнопку **Отмена**, чтобы отменить все изменения и завершить работу с мастером **Определение нового пула сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="31d9c-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="31d9c-117">Нажмите кнопку **Справка**, чтобы открыть контекстно-зависимую справку, аналогичную данной странице.</span><span class="sxs-lookup"><span data-stu-id="31d9c-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="31d9c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="31d9c-118">See also</span></span>

[<span data-ttu-id="31d9c-119">Планирование сервера сохраняемой беседы в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="31d9c-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="31d9c-120">Добавление сервера сохраняемой беседы в топологию Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="31d9c-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
