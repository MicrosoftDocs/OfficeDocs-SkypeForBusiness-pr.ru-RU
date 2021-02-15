---
title: Подготовка отдельного сервера Standard Edition (введение)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: To begin the installation of a Skype for Business Server 2015 Standard Edition server that will hold the Central Management store and other collocated services that you select, you must be logged in as a member of the local Administrators group on the server that will become the Standard Edition server. На странице "Подготовка одного сервера Standard Edition" подробно приводится информация о требованиях к начальной установке. Компьютер должен быть членом домена, в котором он будет развернут, и необходимо успешно завершить подготовку к схеме, лесу и домену для леса.
ms.openlocfilehash: 0523645350c6d6f2c0e42237b944f29193e06555
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829789"
---
# <a name="prepare-single-standard-edition-server-intro"></a>Подготовка отдельного сервера Standard Edition (введение)
 
To begin the installation of a Skype for Business Server 2015 Standard Edition server that will hold the Central Management store and other collocated services that you select, you must be logged in as a member of the local Administrators group on the server that will become the Standard Edition server. На **странице "Подготовка одного сервера Standard Edition"** подробно приводится информация о требованиях к начальной установке. Компьютер должен быть членом домена, в котором он будет развернут, и необходимо успешно завершить подготовку к схеме, лесу и домену для леса.
  
Эта конкретная задача предназначена для установки сервера Standard Edition в качестве первого сервера в инфраструктуре. Эта задача устанавливает центральное хранилище управления, которое SQL Server Express, на сервер Standard Edition. Если у вас уже развернут другой сервер Standard Edition или интерфейсный пул, нажмите кнопку **Отмена**.
  
> [!NOTE]
> После выполнения этой задачи необходимо установить построитель топологий (если он еще не установлен) и настроить документ топологии. Опубликовать документ топологии можно только после того, как станет доступным центральное хранилище управления, которое развертывается при завершении задачи, описанной в этом разделе. 
  

