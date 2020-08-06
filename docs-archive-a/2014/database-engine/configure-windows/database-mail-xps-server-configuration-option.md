---
title: Opção de configuração de servidor Database Mail XPs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Database Mail XPs option
- Database Mail [SQL Server], enabling
ms.assetid: e22c4e63-1792-473b-af11-14a7931ca9ed
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 33ee15e862e0992f39373ec30275040c4fcacc0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575323"
---
# <a name="database-mail-xps-server-configuration-option"></a><span data-ttu-id="e56b4-102">Opção de configuração de servidor Database Mail XPs</span><span class="sxs-lookup"><span data-stu-id="e56b4-102">Database Mail XPs Server Configuration Option</span></span>
  <span data-ttu-id="e56b4-103">Use a opção **DatabaseMail XPs** para habilitar o Database Mail neste servidor.</span><span class="sxs-lookup"><span data-stu-id="e56b4-103">Use the **DatabaseMail XPs** option to enable Database Mail on this server.</span></span> <span data-ttu-id="e56b4-104">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="e56b4-104">The possible values are:</span></span>  
  
-   <span data-ttu-id="e56b4-105">**0** , indicando que o Database Mail não está disponível (padrão).</span><span class="sxs-lookup"><span data-stu-id="e56b4-105">**0** indicating Database Mail is not available (default).</span></span>  
  
-   <span data-ttu-id="e56b4-106">**1** , indicando que o Database Mail está disponível.</span><span class="sxs-lookup"><span data-stu-id="e56b4-106">**1** indicating Database Mail is available.</span></span>  
  
 <span data-ttu-id="e56b4-107">A configuração entra em vigor imediatamente, sem que o servidor seja parado e reiniciado.</span><span class="sxs-lookup"><span data-stu-id="e56b4-107">The setting takes effect immediately without a server stop and restart.</span></span>  
  
 <span data-ttu-id="e56b4-108">Depois de habilitar o Database Mail, você deve configurar um banco de dados de host de Database Mail para usar o Database Mail.</span><span class="sxs-lookup"><span data-stu-id="e56b4-108">After enabling Database Mail, you must configure a Database Mail host database to use Database Mail.</span></span>  
  
 <span data-ttu-id="e56b4-109">Configurar o Database Mail por meio do **Assistente para Configuração do Database Mail** faz com que sejam habilitados os procedimentos armazenados estendidos do Database Mail no banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="e56b4-109">Configuring Database Mail using the **Database Mail Configuration Wizard** enables the Database Mail extended stored procedures in the **msdb** database.</span></span> <span data-ttu-id="e56b4-110">Se usar o **Assistente para Configuração do Database Mail**, você não precisará usar o exemplo de **sp_configure** abaixo.</span><span class="sxs-lookup"><span data-stu-id="e56b4-110">If you use the **Database Mail Configuration Wizard**, you do not have to use the **sp_configure** example below.</span></span>  
  
 <span data-ttu-id="e56b4-111">Definir a opção **Database Mail XPs** como 0 impede que o Database Mail seja iniciado.</span><span class="sxs-lookup"><span data-stu-id="e56b4-111">Setting the **Database Mail XPs** option to 0 prevents Database Mail from starting.</span></span> <span data-ttu-id="e56b4-112">Se estiver em execução quando a opção for definida como 0, ele continuará em execução e enviando emails até estar ocioso pelo tempo configurado na opção **DatabaseMailExeMinimumLifeTime** .</span><span class="sxs-lookup"><span data-stu-id="e56b4-112">If it is running when the option is set to 0, it continues to run and send mail until it is idle for the time configured in the **DatabaseMailExeMinimumLifeTime** option.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e56b4-113">Exemplos</span><span class="sxs-lookup"><span data-stu-id="e56b4-113">Examples</span></span>  
 <span data-ttu-id="e56b4-114">O exemplo a seguir habilita os procedimentos armazenados estendidos do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="e56b4-114">The following example enables the Database Mail extended stored procedures.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'Database Mail XPs', 1;  
GO  
RECONFIGURE  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="e56b4-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e56b4-115">See Also</span></span>  
 [<span data-ttu-id="e56b4-116">Database Mail</span><span class="sxs-lookup"><span data-stu-id="e56b4-116">Database Mail</span></span>](../../relational-databases/database-mail/database-mail.md)  
  
  
