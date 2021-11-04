---
title: Добавление IP-параметров пограничного сервера
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.localizationpriority: medium
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Microsoft Lync Server 2013 позволяет настраивать адреса IPv4 и IPv6 для каждого интерфейса для пула Edge Server и Edge. Для этого выполните следующие действия:'
ms.openlocfilehash: b26fdd7dccca93f04c5fa5d9ee40e644143f8f9c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776379"
---
# <a name="add-edge-server-ip-options"></a>Добавление IP-параметров пограничного сервера
 
Microsoft Lync Server 2013 позволяет настраивать адреса IPv4 и IPv6 для каждого интерфейса для пула Edge Server и Edge. Для этого выполните следующие действия:
  
- **Включить IPv4 на** внутреннем интерфейсе: Выберите контрольный ящик, если вы хотите применить адрес IPv4 к внутреннему интерфейсу edge Server или Edge Pool
    
- **Включить IPv6 во внутреннем интерфейсе:** Выберите контрольный ящик, если вы хотите применить адрес IPv6 к внутреннему интерфейсу edge Server или Edge Pool
    
- **Включить IPv4 на внешнем интерфейсе:** Выберите контрольный ящик, если вы хотите применить адрес IPv4 к внешнему интерфейсу edge Server или Edge Pool
    
- **Включить IPv6 на внешнем интерфейсе:** Выберите контрольный ящик, если вы хотите применить адрес IPv6 к внешнему интерфейсу edge Server или Edge Pool
    
Вы также можете настроить пул Edge Server или Edge для использования сетевого адреса для внешних IP-адресов. Для этого установите флажок **Внешний IP-адрес данного пограничного пула преобразуется системой NAT**.
  
Поддержка NAT. Преобразование сетевых адресов (NAT) не поддерживается при использовании балансировки нагрузки оборудования, поэтому не выбирайте параметр NAT при развертывании пула пограничного сервера в сочетании с балансировкой нагрузки оборудования.
  

