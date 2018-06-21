---
title: Проверка репликации раздела леса
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 'Убедитесь, что репликация глобального каталога и создания объектов во время подготовки леса имеют прошел успешно, выполните следующие действия:'
ms.openlocfilehash: f45fb8f6c24d0cd9e8bcc108afbd9ec8cc9aa607
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/20/2018
ms.locfileid: "19964528"
---
# <a name="verify-replication-of-forest-preparation"></a><span data-ttu-id="675ff-103">Проверка репликации раздела леса</span><span class="sxs-lookup"><span data-stu-id="675ff-103">Verify Replication of Forest Preparation</span></span>
 
<span data-ttu-id="675ff-104">Убедитесь, что репликация глобального каталога и создания объектов во время подготовки леса имеют прошел успешно, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="675ff-104">To confirm that the replication of the Global Catalog and the creation of objects during Forest Preparation have been successful, do the following:</span></span>
  
1. <span data-ttu-id="675ff-105">На контроллере домена (желательно в месте, удаленном от других контроллеров домена) в лесу, для которого выполнялась подготовка, откройте окно **Пользователи и компьютеры Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="675ff-105">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
2. <span data-ttu-id="675ff-106">В окне **Пользователи и компьютеры Active Directory** разверните имя домена своего леса или дочернего домена.</span><span class="sxs-lookup"><span data-stu-id="675ff-106">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
3. <span data-ttu-id="675ff-107">Щелкните контейнер **Users** на левой панели и найдите универсальной группы CsAdministrator в правой области.</span><span class="sxs-lookup"><span data-stu-id="675ff-107">Click the **Users** container on the left side pane and look for the Universal group CsAdministrator in the right side pane.</span></span> <span data-ttu-id="675ff-108">При наличии CsAdministrator (среди восемь другие новые универсальные группы, начинающихся с Cs) репликации Подготовка леса выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="675ff-108">If CsAdministrator (among eight other new Universal groups that begin with Cs) is present, replication of the Forest Preparation has been successful.</span></span>
    
4. <span data-ttu-id="675ff-109">Если группы не указан, принудительной репликации, или подождите 15 минут и обновить в правой области.</span><span class="sxs-lookup"><span data-stu-id="675ff-109">If the group(s) is not yet present, you can force the replication or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="675ff-110">Если группы появились, репликация завершена.</span><span class="sxs-lookup"><span data-stu-id="675ff-110">When the groups are present, replication is complete.</span></span>
    
> [!TIP]
> <span data-ttu-id="675ff-111">Если вы хотите просмотрите файлы журнала, создаваемые с Скайп для мастер развертывания Business Server, их можно найти на компьютере, на котором запускался мастер развертывания в каталоге пользователи из доменных служб Active Directory пользователя, выполнившего действие.</span><span class="sxs-lookup"><span data-stu-id="675ff-111">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="675ff-112">Например, если пользователь вошел в систему от имени администратора домена в домене Contoso.net, файлов журнала, находятся в: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="675ff-112">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

