---
title: Импорт сертификата (введение)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertImportBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 474fac52-0b11-45dd-a211-fd2f1727238b
ROBOTS: NOINDEX, NOFOLLOW
description: Для импорта сертификата необходимо указать путь к файлу сертификата. В поле Выбор файла сертификата введите полный путь и имя файла или нажмите кнопку Обзор и перейдите к расположению, в котором указан путь и имя файла (обычно. p7b, PFX или CER-файл).
ms.openlocfilehash: b04f8a2ca2e6d3104f4b36e4bc04b6cdd3c61940
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275554"
---
# <a name="import-certificate-intro"></a><span data-ttu-id="4e4f7-104">Импорт сертификата (введение)</span><span class="sxs-lookup"><span data-stu-id="4e4f7-104">Import Certificate (Intro)</span></span>
 
<span data-ttu-id="4e4f7-105">Для импорта сертификата необходимо указать путь к файлу сертификата.</span><span class="sxs-lookup"><span data-stu-id="4e4f7-105">To import a certificate, you must provide a path to the certificate file.</span></span> <span data-ttu-id="4e4f7-106">В поле **Выбор файла сертификата** введите полный путь и имя файла или нажмите кнопку **Обзор** и перейдите к расположению, в котором указан путь и имя файла (обычно. p7b, PFX или CER-файл).</span><span class="sxs-lookup"><span data-stu-id="4e4f7-106">In the **Select Certificate file** text box, you can either type the full path and file name, or click the **Browse** button and navigate to the path location and the file name (typically, a .p7b, .pfx, or .cer file).</span></span>
  
<span data-ttu-id="4e4f7-107">Если сертификат имеет закрытый ключ, установите флажок файл сертификата с флажком, который **включает закрытый ключ сертификата**.</span><span class="sxs-lookup"><span data-stu-id="4e4f7-107">If the certificate contains a private key, select the check box **Certificate file contains certificate's private key**.</span></span> <span data-ttu-id="4e4f7-108">Если установлен этот флажок, ввод текста **пароля** включен.</span><span class="sxs-lookup"><span data-stu-id="4e4f7-108">When this check box is selected, the **Password** text input is enabled.</span></span> <span data-ttu-id="4e4f7-109">Если у вас есть сертификат, связанный с закрытым ключом, пароль обычно размещается на закрытом ключе при создании сертификата.</span><span class="sxs-lookup"><span data-stu-id="4e4f7-109">If you have a certificate with a private key associated with it, a password is usually placed on the private key when the certificate is created.</span></span> <span data-ttu-id="4e4f7-110">Вы можете ввести пароль для закрытого ключа, чтобы разрешить импорт сертификата и закрытого ключа в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="4e4f7-110">You input the password for the private key to allow the certificate and the private key to be imported into the certificate store.</span></span> <span data-ttu-id="4e4f7-111">После того как вы предоставили сведения о пути к файлу сертификата и, при необходимости, пароль закрытого ключа, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4e4f7-111">When you have provided the information for the certificate file path, and optionally the private key password, if required, click **Next**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4e4f7-112">Если вы не знаете пароль для закрытого ключа, импорт завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="4e4f7-112">If you do not know the password for the private key, the import will fail.</span></span> 
  

