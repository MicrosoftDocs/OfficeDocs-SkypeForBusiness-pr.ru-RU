---
title: Добавление IP-параметров пограничного сервера
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Microsoft Lync Server 2013 позволяет настраивать адреса IPv4 и IPv6 для каждого интерфейса для edge Server и пула. Для этого выполните следующие действия:'
ms.openlocfilehash: d8bfed4d7318133d33d733953cfcf472aa0e88ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815209"
---
# <a name="add-edge-server-ip-options"></a>Добавление IP-параметров пограничного сервера
 
Microsoft Lync Server 2013 позволяет настраивать адреса IPv4 и IPv6 для каждого интерфейса для edge Server и пула. Для этого выполните следующие действия:
  
- **Включить IPv4 во** внутреннем интерфейсе: если нужно применить IPv4-адрес к внутреннему интерфейсу edge Server или пула edge
    
- **Включить IPv6 во** внутреннем интерфейсе: если нужно применить IPv6-адрес к внутреннему интерфейсу edge Server или пула edge
    
- **Включить IPv4 на** внешнем интерфейсе: если вы хотите применить IPv4-адрес к внешнему интерфейсу edge Server или пула edge
    
- **Включить IPv6 на** внешнем интерфейсе: если вы хотите применить IPv6-адрес к внешнему интерфейсу edge Server или пула edge
    
Вы также можете настроить на использование адреса перевода сетевых адресов для внешних IP-адресов. Для этого установите флажок **Внешний IP-адрес данного пограничного пула преобразуется системой NAT**.
  
Поддержка NAT. Преобразование сетевых адресов (NAT) не поддерживается при использовании балансировки нагрузки оборудования, поэтому не выбирайте параметр NAT при развертывании пула пограничного сервера в сочетании с балансировкой нагрузки оборудования.
  

