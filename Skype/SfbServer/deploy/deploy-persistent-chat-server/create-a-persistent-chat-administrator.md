---
title: Создание администратора сохраняемого чата в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Аннотация: Ознакомьтесь с этой статьей, чтобы получить сведения о том, как создать учетную запись администратора сервера чата, чтобы включить начальную настройку и управление службами сохраняемого чата в Skype для бизнеса Server 2015.'
ms.openlocfilehash: 1b593f1de776f1896d43bab35a15af7b6bcf7245
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273884"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="4b620-103">Создание администратора сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="4b620-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4b620-104">**Сводка:** В этой статье рассказывается о том, как создать роль администратора сервера учетных данных для обеспечения начальной настройки и управления службами сохраняемого чата в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4b620-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="4b620-105">В Skype для бизнеса Server пользователи, которые выполняют определенные задачи, должны быть назначены как участники одной или нескольких конкретных групп.</span><span class="sxs-lookup"><span data-stu-id="4b620-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="4b620-106">Управление доступом на основе ролей (RBAC) используется для предоставления привилегий путем назначения пользователям стандартных административных ролей в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4b620-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="4b620-107">These roles correspond to universal security groups in Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="4b620-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="4b620-108">Участникам группы безопасности "постоянный чат" Ксперсистентчатадминистратор предоставлен доступ к командлетам сервера сохраняемого чата, которые можно выполнить с помощью командной консоли Skype для бизнеса Server или Skype для бизнеса. Панель управления сервера.</span><span class="sxs-lookup"><span data-stu-id="4b620-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="4b620-109">Прежде чем настраивать и администрировать сервер сохраняемого чата, необходимо убедиться, что заданы соответствующие права и разрешения пользователей и в группу безопасности администраторов сохраняемого чата добавлены все пользователи, которые будут действовать как администраторы сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="4b620-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
> [!NOTE] 
> <span data-ttu-id="4b620-110">Сохраняемый чат доступен в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4b620-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="4b620-111">Эта функция доступна в Teams.</span><span class="sxs-lookup"><span data-stu-id="4b620-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="4b620-112">Дополнительные сведения можно найти в разделе [путешествие из Skype для бизнеса в Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="4b620-112">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="4b620-113">Если вы хотите использовать сохраняемый чат, вы можете либо перенести пользователей, которым требуются эти функции, в Teams, либо продолжить работу с Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4b620-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="4b620-114">Create a Persistent Chat administrator</span><span class="sxs-lookup"><span data-stu-id="4b620-114">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="4b620-115">Чтобы добавить пользователя в группу постоянного чата Administrator, Ксперсистентчатадминистратор, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="4b620-115">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="4b620-116">Используя учетную запись с разрешением на изменение членства группы Active Directory, выполните вход на компьютер, где был установлен компонент "Пользователи и компьютеры Active Directory".</span><span class="sxs-lookup"><span data-stu-id="4b620-116">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="4b620-117">Нажмите кнопку "Пуск", выберите "Все программы", "Администрирование" и затем "Пользователи и компьютеры Active Directory".</span><span class="sxs-lookup"><span data-stu-id="4b620-117">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="4b620-118">В окне "Пользователи и компьютеры Active Directory" разверните имя своего домена и щелкните контейнер "Пользователи".</span><span class="sxs-lookup"><span data-stu-id="4b620-118">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="4b620-119">Щелкните группу безопасности CsPersistentChatAdministrator правой кнопкой мыши и выберите пункт "Свойства".</span><span class="sxs-lookup"><span data-stu-id="4b620-119">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="4b620-120">В диалоговом окне "Свойства" на вкладке "Члены" нажмите кнопку "Добавить".</span><span class="sxs-lookup"><span data-stu-id="4b620-120">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="4b620-121">В диалоговом окне выбора пользователей, компьютеров, контактов или групп введите имя пользователя или отображаемое имя для пользователя, добавляемого в группу, в поле "Введите имена выбираемых объектов" и нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="4b620-121">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="4b620-122">В диалоговом окне "Свойства" нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="4b620-122">In the Properties dialog box, click OK.</span></span>
    

