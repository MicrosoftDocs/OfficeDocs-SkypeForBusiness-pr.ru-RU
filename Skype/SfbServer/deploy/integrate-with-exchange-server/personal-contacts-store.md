---
title: Настройка хранилища личных контактов на клиентских компьютерах для Скайп для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Сводка: Настройка личных хранилище контактов, используемых Exchange Server 2016 или Exchange Server 2013 и Скайп для Business Server.'
ms.openlocfilehash: 311bab825412bae79c240ddb0f923c693b97103e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21012902"
---
# <a name="configure-the-personal-contacts-store-on-client-computers-for-skype-for-business-server"></a>Настройка хранилища личных контактов на клиентских компьютерах для Скайп для Business Server
 
**Сводка:** Настройка хранилища личных контактов, используемых Exchange Server 2016 или Exchange Server 2013 и Скайп для Business Server.
  
Если вы реализуете интеграцию Скайп Business Server и Exchange Server 2016 или Exchange Server 2013, следует настроить хранилище личных контактов на все клиентские компьютеры под управлением Скайп для бизнеса. В частности необходимо настроить Скайп для использования Exchange в качестве хранилища личных контактов и, в то же время, убедитесь, что пользователи не могут переопределить это решение. Это можно сделать, создав и настроив значение реестра на каждом клиентском компьютере.
  
Обратите внимание на то, что это не требуется на компьютерах под управлением Скайп для бизнеса.
  
Чтобы настроить данное значение на одном компьютере, выполните следующие действия:
  
1. На клиентском компьютере нажмите кнопку **Пуск** и выберите команду **Выполнить**.
    
2. В диалоговом окне **Выполнить** введите regedit, а затем нажмите ВВОД.
    
3. В редакторе реестра последовательно разверните узлы **HKEY_LOCAL_MACHINE**, **Software**, **Policies**, **Microsoft** и **Communicator**.
    
4. Щелкните элемент **Communicator** правой кнопкой мыши, наведите указатель на пункт **Создать** и выберите пункт **Параметр DWORD (32-разрядный)**.
    
5. После создания параметра введите PersonalContactStoreOverride и нажмите клавишу ВВОД, чтобы переименовать параметр.
    
6. Убедитесь, что значение PersonalContactStoreOverride равно 0, а затем закройте редактор реестра.
    
Если нужно внести это изменение на нескольких компьютерах, это можно сделать, создав пользовательский объект групповой политики. Для получения дополнительных сведений, обратитесь к документации групповой политики на [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543).
  

