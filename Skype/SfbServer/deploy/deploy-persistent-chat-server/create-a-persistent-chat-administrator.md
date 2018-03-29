---
title: Создание администратора сохраняемого чата в Skype для бизнеса Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Сводка: Прочтите этот раздел, чтобы узнать, как создать роль администратора сервера сохраняемого чата для включения начальной настройки и управления службы Persistent Chat в Скайп для Business Server 2015.'
ms.openlocfilehash: 4efe5dff2821784a24f51712b8a19dad83e47c3b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="a8a4b-103">Создание администратора сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="a8a4b-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a8a4b-104">**Сводка:** Прочтите этот раздел, чтобы узнать, как создать роль администратора сервера сохраняемого чата для включения начальной настройки и управления службы Persistent Chat в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a8a4b-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a8a4b-105">В Скайп Business Server пользователей, выполняющих определенные задачи необходимо быть назначен в качестве членов одной или нескольких конкретных групп.</span><span class="sxs-lookup"><span data-stu-id="a8a4b-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="a8a4b-106">Элемент управления доступа на основе ролей (RBAC) используется для предоставления прав, назначив пользователям предварительно заданных Скайп для административных ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="a8a4b-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="a8a4b-107">Эти роли соответствуют универсальных групп безопасности в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a8a4b-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="a8a4b-108">Члены группы безопасности Persistent Chat Administrator, CsPersistentChatAdministrator, будет предоставлен доступ к командлетов сервера сохраняемого чата, которые могут быть выполнены с помощью Скайп для консоли Business Server или Скайп для бизнеса Панель управления сервера.</span><span class="sxs-lookup"><span data-stu-id="a8a4b-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="a8a4b-109">Прежде чем настраивать и администрировать сервер сохраняемого чата, необходимо убедиться, что заданы соответствующие права и разрешения пользователей и в группу безопасности администраторов сохраняемого чата добавлены все пользователи, которые будут действовать как администраторы сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="a8a4b-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="a8a4b-110">Создание администратора сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="a8a4b-110">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="a8a4b-111">Чтобы добавить пользователя в группу безопасности Persistent Chat Administrator CsPersistentChatAdministrator, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a8a4b-111">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="a8a4b-112">Используя учетную запись с разрешением на изменение членства группы Active Directory, выполните вход на компьютер, где был установлен компонент "Пользователи и компьютеры Active Directory".</span><span class="sxs-lookup"><span data-stu-id="a8a4b-112">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="a8a4b-113">Нажмите кнопку "Пуск", выберите "Все программы", "Администрирование" и затем "Пользователи и компьютеры Active Directory".</span><span class="sxs-lookup"><span data-stu-id="a8a4b-113">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="a8a4b-114">В окне "Пользователи и компьютеры Active Directory" разверните имя своего домена и щелкните контейнер "Пользователи".</span><span class="sxs-lookup"><span data-stu-id="a8a4b-114">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="a8a4b-115">Щелкните группу безопасности CsPersistentChatAdministrator правой кнопкой мыши и выберите пункт "Свойства".</span><span class="sxs-lookup"><span data-stu-id="a8a4b-115">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="a8a4b-116">В диалоговом окне "Свойства" на вкладке "Члены" нажмите кнопку "Добавить".</span><span class="sxs-lookup"><span data-stu-id="a8a4b-116">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="a8a4b-117">В диалоговом окне выбора пользователей, компьютеров, контактов или групп введите имя пользователя или отображаемое имя для пользователя, добавляемого в группу, в поле "Введите имена выбираемых объектов" и нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="a8a4b-117">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="a8a4b-118">В диалоговом окне "Свойства" нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="a8a4b-118">In the Properties dialog box, click OK.</span></span>
    

