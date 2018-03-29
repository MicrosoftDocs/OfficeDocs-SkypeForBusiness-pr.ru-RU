---
title: Добавление файлового хранилища сохраняемого чата
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: Необходимо указать общий файловый ресурс, который будет использоваться в качестве хранилища файлов для сервера Standard Edition или пула переднего плана Enterprise Edition. В качестве хранилища файлов можно использовать существующий общий файловый ресурс. Кроме того, можно добавить новый общий файловый ресурс, указав полное доменное имя файлового сервера, на котором расположен общий файловый ресурс, и имя папки для нового общего файлового ресурса.
ms.openlocfilehash: 76b116d469bf6369174815d6b396a64149518f17
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="add-persistent-chat-file-store"></a><span data-ttu-id="c639d-104">Добавление файлового хранилища сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="c639d-104">Add Persistent Chat File Store</span></span>
 
<span data-ttu-id="c639d-p102">Необходимо указать общий файловый ресурс, который будет использоваться в качестве хранилища файлов для сервера Standard Edition или пула переднего плана Enterprise Edition. В качестве хранилища файлов можно использовать существующий общий файловый ресурс. Кроме того, можно добавить новый общий файловый ресурс, указав полное доменное имя файлового сервера, на котором расположен общий файловый ресурс, и имя папки для нового общего файлового ресурса.</span><span class="sxs-lookup"><span data-stu-id="c639d-p102">You must specify a file share to be used as the file store for the Standard Edition server or Enterprise Edition Front End pool. You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c639d-107">Файловый ресурс для Скайп для Business Server не может быть расположена на сервере переднего плана Enterprise Edition, но может быть найдена на сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c639d-107">The file share for Skype for Business Server cannot be located on the Enterprise Edition Front End Server, but can be located on a Standard Edition server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c639d-108">Вы можете определить общую папку файлов в построителе топологий перед ее созданием, однако вам следует поместить эту папку в расположение, заданное до публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="c639d-108">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location you define before you publish the topology.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c639d-109">При добавлении серверов сохраняемого чата или серверов сохраняемого чата пула в топологию, Topology Builder должны иметь возможность создать файл хранения и настройка управления доступом список (доступом) в общей папке, которое будет использоваться для хранения файла.</span><span class="sxs-lookup"><span data-stu-id="c639d-109">When you add a Persistent Chat Server or Persistent Chat Server pool to your topology, Topology Builder must be able to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="c639d-110">При запуске построителя топологии для публикации новой топологии необходимо войти в систему с использованием учетной записи с полными правами на управление (чтение/запись/изменение) для общего файлового ресурса.</span><span class="sxs-lookup"><span data-stu-id="c639d-110">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c639d-111">См. также</span><span class="sxs-lookup"><span data-stu-id="c639d-111">See also</span></span>

#### 

[<span data-ttu-id="c639d-112">Планирование для сервера сохраняемого чата в Скайп Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c639d-112">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="c639d-113">Добавление сервера сохраняемого чата для вашей Скайп для топологии Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c639d-113">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="c639d-114">Аппаратные и программные требования для сервера сохраняемого чата в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c639d-114">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="c639d-115">Требования к серверу для Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c639d-115">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="c639d-116">Основные сведения о топологии для Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c639d-116">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)

