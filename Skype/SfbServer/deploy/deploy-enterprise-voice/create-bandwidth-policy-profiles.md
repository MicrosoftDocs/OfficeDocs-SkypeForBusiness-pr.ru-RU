---
title: Создание профилей политики пропускной способности в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: Создание или изменение политик пропускной способности, которые используются Корпоративная голосовая связь контроля допуска звонков в Skype для бизнеса Server.
ms.openlocfilehash: ac80ebb8b61a763efc0077f267a024a21a359b5d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824850"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a>Создание профилей политики пропускной способности в Skype для бизнеса Server 
 
Создание или изменение политик пропускной способности, которые используются Корпоративная голосовая связь контроля допуска звонков в Skype для бизнеса Server. 
  
Политики пропускной способности задают ограничения пропускной способности сети для режимов передачи аудио и видеоданных в реальном времени. Политики пропускной способности применяются к профилям политикbandwidth, которые можно применять к нескольким сетевым сайтам для контроля допуска вызовов.
  
Рекомендации по ограничениям пропускной способности, которые необходимо установить в развертывании КОНТРОЛЯ допуска звонков, см. в документе "Планирование контроля допуска звонков [в Skype для бизнеса Server".](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)
  
Примеры политик, созданных в следующей процедуре, задают ограничения для общего трафика аудиоданных, отдельных аудиосеансов, общего трафика видеоданных и отдельных видеосеансов. Например, профиль политики пропускной способности 5Mb_Link задает следующие ограничения: 
  
- Аудиоданные: 2 000 кбит/с
    
- Аудиосеансы: 200 кбит/с
    
- Видеоданные: 1 400 кбит/с
    
- Видеосеансы: 700 кбит/с
    
> [!NOTE]
> Минимальное значение для аудиосеанса 40 кбит/с. Минимальное значение для видеосеанса 100 кбит/с. 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a>Создание профилей политик пропускной способности с помощью skype для бизнеса Server Management Shell

1. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
2. Выполните командлет New-CsNetworkBandwidthPolicyProfile для каждого создаваемого профиля политики пропускной способности. Пример:
    
   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a>Создание профилей политики пропускной способности с помощью панели управления Skype для бизнеса Server

1. Откройте панель управления Skype для бизнеса Server.
    
2. В левой панели навигации щелкните **Network Configuration** (Параметры сети).
    
3. Нажмите кнопку навигации **Policy Profile** (Профиль политики).
    
4. Щелкните **New** (Создать).
    
5. На странице **New Policy Profile** (Создание профиля политики) введите имя профиля политики пропускной способности в поле **Name** (Имя).
    
6. Щелкните **Audio limit** (Ограничение для аудиоданных) и затем введите максимальную скорость (кбит/с) для всех аудиосеансов.
    
7. Щелкните **Audio session limit** (Ограничение для аудиосеанса) и затем введите максимальную скорость (кбит/с) для отдельного аудиосеанса.
    
8. Щелкните **Video limit** (Ограничение для видеоданных) и затем введите максимальную скорость (кбит/с) для всех видеосеансов.
    
9. Щелкните **Video session limit** (Ограничение для видеосеанса) и затем введите максимальную скорость (кбит/с) для отдельного видеосеанса.
    
10. В поле **Description** (Описание) введите дополнительные сведения о профиле политики пропускной способности (необязательно).
    
11. Щелкните **Commit** (Применить).
    
12. Чтобы завершить создание профилей политики пропускной способности для топологии, повторите шаги с 4 по 11 для остальных профилей политики пропускной способности.
    
## <a name="see-also"></a>См. также

[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)
