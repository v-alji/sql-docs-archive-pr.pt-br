---
title: Criar uma função definida pelo usuário | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: c4128993-2333-48c7-84b1-e51cdcea393d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a0ee905c2636e20315c2180a6be8f8e40f76d5f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572616"
---
# <a name="create-a-user-defined-role"></a><span data-ttu-id="a8f2b-102">Criar uma função definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="a8f2b-102">Create a User-Defined Role</span></span>
    
### <a name="to-create-a-user-defined-role"></a><span data-ttu-id="a8f2b-103">Para criar uma função definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="a8f2b-103">To create a user-defined role</span></span>  
  
1.  <span data-ttu-id="a8f2b-104">Abra o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8f2b-104">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="a8f2b-105">Clique em **Pesquisador de Objetos** no menu **Exibir** .</span><span class="sxs-lookup"><span data-stu-id="a8f2b-105">Click **Object Explorer** on the **View** menu.</span></span>  
  
3.  <span data-ttu-id="a8f2b-106">Na barra de ferramentas do Pesquisador de Objetos, clique em **Conectar**e clique em **Mecanismo de Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="a8f2b-106">On the Object Explorer toolbar, click **Connect**, and then click **Database Engine**.</span></span>  
  
4.  <span data-ttu-id="a8f2b-107">Na caixa de diálogo **Conectar ao Servidor** , forneça um nome de um servidor e selecione um modo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="a8f2b-107">In the **Connect to Server** dialog box, provide a server name and select an authentication mode.</span></span> <span data-ttu-id="a8f2b-108">Você pode usar um ponto (.), (local) ou `localhost` para indicar o servidor local.</span><span class="sxs-lookup"><span data-stu-id="a8f2b-108">You can use a period (.), (local), or `localhost` to indicate the local server.</span></span>  
  
5.  <span data-ttu-id="a8f2b-109">Clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="a8f2b-109">Click **Connect**.</span></span>  
  
6.  <span data-ttu-id="a8f2b-110">Expanda Bancos de Dados, Bancos de Dados do Sistema, msdb, Segurança e Funções.</span><span class="sxs-lookup"><span data-stu-id="a8f2b-110">Expand Databases, System Databases, msdb, Security, and Roles.</span></span>  
  
7.  <span data-ttu-id="a8f2b-111">No nó Funções, clique com o botão direito do mouse em Funções de Banco de Dados e clique em **Nova Função de Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="a8f2b-111">In the Roles node, right-click Database Roles, and click **New Database Role**.</span></span>  
  
8.  <span data-ttu-id="a8f2b-112">Na página Geral, forneça um nome e, opcionalmente, especifique um proprietário e esquemas proprietários e adicione membros da função.</span><span class="sxs-lookup"><span data-stu-id="a8f2b-112">On the General page, provide a name and optionally, specify an owner and owned schemas and add role members.</span></span>  
  
9. <span data-ttu-id="a8f2b-113">Opcionalmente, clique em **Permissões** e configure as permissões de objeto.</span><span class="sxs-lookup"><span data-stu-id="a8f2b-113">Optionally, click **Permissions** and configure object permissions.</span></span>  
  
10. <span data-ttu-id="a8f2b-114">Opcionalmente, clique em **Propriedades Estendidas** e configure qualquer propriedade estendida.</span><span class="sxs-lookup"><span data-stu-id="a8f2b-114">Optionally, click **Extended Properties** and configure any extended properties.</span></span>  
  
11. <span data-ttu-id="a8f2b-115">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8f2b-115">Click **OK**.</span></span>  
  
  
