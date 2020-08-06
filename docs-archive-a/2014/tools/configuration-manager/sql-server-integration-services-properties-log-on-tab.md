---
title: Propriedades do SQL Server Integration Services (guia Logon) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: c0eb1b87-6bb0-475e-8492-0fd3c3f910ea
author: stevestein
ms.author: sstein
ms.openlocfilehash: dfef02a82872ea1df25e7ccb8526e488aaa5f406
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683856"
---
# <a name="sql-server-integration-services-properties-log-on-tab"></a>Propriedades do SQL Server Integration Services (guia Fazer Logon)
  Use a guia **Fazer Logon** da caixa de diálogo [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] **Propriedades** do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para especificar a conta usada pelo serviço e também para iniciar e parar o serviço.  
  
## <a name="options"></a>Opções  
 **Conta Sistema Local**  
 Especifique uma conta Sistema Local que não requeira uma senha. Porém, essa conta pode restringir a interação do serviço com outros servidores, dependendo dos privilégios concedidos a ela.  
  
 **Esta conta**  
 Especifique uma conta de usuário local ou de domínio que usa a Autenticação do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows. [!INCLUDE[msCoName](../../includes/msconame-md.md)] recomenda usar uma conta de usuário do domínio com direitos mínimos para serviços. Para obter informações sobre como selecionar uma conta, pesquise o tópico "Configurando as contas de serviço do Windows" nos Manuais Online.  
  
 **Nome da Conta**  
 Especifique o nome da conta local ou de usuário de domínio.  
  
 **Senha**  
 Digite a senha da conta.  
  
 **Confirmar senha**  
 Digite a senha da conta novamente.  
  
 **Iniciar**  
 Inicie o serviço.  
  
 **Parar**  
 Parar o serviço.  
  
 **Pausar**  
 Pausar o serviço.  
  
 **Retomar**  
 Retomar um serviço pausado.  
  
  
