---
title: Проверка репликации подготовки леса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
ROBOTS: NOINDEX, NOFOLLOW
description: Чтобы убедиться в том, что репликация глобального каталога и создание объектов во время подготовки леса выполнена успешно, выполните указанные ниже действия.
ms.openlocfilehash: c7fe425dcbecf2bfba02d4862bc3a29b75e16910
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303348"
---
# <a name="verify-replication-of-forest-preparation"></a><span data-ttu-id="05f5e-103">Проверка репликации подготовки леса</span><span class="sxs-lookup"><span data-stu-id="05f5e-103">Verify Replication of Forest Preparation</span></span>
 
<span data-ttu-id="05f5e-104">Чтобы убедиться в том, что репликация глобального каталога и создание объектов во время подготовки леса выполнена успешно, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="05f5e-104">To confirm that the replication of the Global Catalog and the creation of objects during Forest Preparation have been successful, do the following:</span></span>
  
1. <span data-ttu-id="05f5e-105">На контроллере домена (желательно в месте, удаленном от других контроллеров домена) в лесу, для которого выполнялась подготовка, откройте окно **Пользователи и компьютеры Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="05f5e-105">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
2. <span data-ttu-id="05f5e-106">В окне **Пользователи и компьютеры Active Directory** разверните имя домена своего леса или дочернего домена.</span><span class="sxs-lookup"><span data-stu-id="05f5e-106">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
3. <span data-ttu-id="05f5e-107">Щелкните контейнер **Пользователи** в левой части экрана и найдите универсальную группу ксадминистратор в правой области.</span><span class="sxs-lookup"><span data-stu-id="05f5e-107">Click the **Users** container on the left side pane and look for the Universal group CsAdministrator in the right side pane.</span></span> <span data-ttu-id="05f5e-108">Если присутствует Ксадминистратор (среди восьми других новых универсальных групп, начинающихся с CS), репликация подготовки леса была выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="05f5e-108">If CsAdministrator (among eight other new Universal groups that begin with Cs) is present, replication of the Forest Preparation has been successful.</span></span>
    
4. <span data-ttu-id="05f5e-109">Если группы еще нет в списке, вы можете принудительно выполнить репликацию или подождать 15 минут и обновить ее в правой части окна.</span><span class="sxs-lookup"><span data-stu-id="05f5e-109">If the group(s) is not yet present, you can force the replication or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="05f5e-110">Если группы появились, репликация завершена.</span><span class="sxs-lookup"><span data-stu-id="05f5e-110">When the groups are present, replication is complete.</span></span>
    
> [!TIP]
> <span data-ttu-id="05f5e-111">Если вы хотите просмотреть файлы журнала, созданные с помощью мастера развертывания Skype для бизнеса Server, вы можете найти их на компьютере, на котором был запущен мастер развертывания, в каталоге Users доменных служб Active Directory, выполнившего этот шаг.</span><span class="sxs-lookup"><span data-stu-id="05f5e-111">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="05f5e-112">Например, если пользователь выполнил вход в качестве администратора домена в Contoso.net домена, файлы журнала находятся в: К:\усерс\администратор.контосо\аппдата\локал\темп</span><span class="sxs-lookup"><span data-stu-id="05f5e-112">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

