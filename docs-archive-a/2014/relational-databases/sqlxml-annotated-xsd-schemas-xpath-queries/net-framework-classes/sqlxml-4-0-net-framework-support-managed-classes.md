---
title: Classes gerenciadas SQLXML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- .NET Framework [SQLXML], Managed Classes
- SQL Server .NET Data Provider
- Managed Classes [SQLXML], about managed classes
- providers [SQLXML], SQL Server .NET Data Provider
- data providers [SQLXML], SQL Server .NET Data Provider
- Managed Classes [SQLXML]
- XML [SQLXML]
- SQLXML Managed Classes
- providers [SQLXML], SQLXML Managed Classes
- data providers [SQLXML], SQLXML Managed Classes
- SQLXML, Managed Classes
ms.assetid: 73a5faeb-dabf-4895-acb5-a9651b646065
author: rothja
ms.author: jroth
ms.openlocfilehash: bb8d2d4f2d2fc512901e4ad37f0e46cf696b9475
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568411"
---
# <a name="sqlxml-managed-classes"></a><span data-ttu-id="6da92-102">Classes gerenciadas SQLXML</span><span class="sxs-lookup"><span data-stu-id="6da92-102">SQLXML Managed Classes</span></span>
  <span data-ttu-id="6da92-103">As classes gerenciadas [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML expõem a funcionalidade do SQLXML 4.0 dentro do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6da92-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML Managed Classes exposes the functionality of SQLXML 4.0 inside the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span></span> <span data-ttu-id="6da92-104">Com as classes gerenciadas SQLXML, você pode escrever um aplicativo C# para acessar dados XML de uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], trazer os dados para o ambiente .NET Framework, processar os dados e enviar as atualizações de volta para o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] como um DiffGram para aplicar as atualizações.</span><span class="sxs-lookup"><span data-stu-id="6da92-104">With SQLXML Managed Classes, you can write a C# application to access XML data from an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], bring the data into the .NET Framework environment, process the data, and send the updates back to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as a DiffGram to apply the updates.</span></span> <span data-ttu-id="6da92-105">Use um esquema de mapeamento ao aplicar atualizações a um banco de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usando classes gerenciadas SQLXML.</span><span class="sxs-lookup"><span data-stu-id="6da92-105">You must use a mapping schema when applying updates to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database using SQLXML Managed Classes.</span></span> <span data-ttu-id="6da92-106">Para obter um exemplo funcional, consulte [acessando a funcionalidade SQLXML no ambiente .net](accessing-sqlxml-functionality-in-the-net-environment.md).</span><span class="sxs-lookup"><span data-stu-id="6da92-106">For a working sample, see [Accessing SQLXML Functionality in the .NET Environment](accessing-sqlxml-functionality-in-the-net-environment.md).</span></span>  
  
 <span data-ttu-id="6da92-107">Para usar as classes gerenciadas SQLXML com o SQLXML 4.0, é necessário instalar o Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6da92-107">To use the SQLXML Managed Classes with SQLXML 4.0, you must install Microsoft Visual Studio.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6da92-108">O .NET Framework inclui o .NET Data Provider do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6da92-108">The .NET Framework includes the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .NET Data Provider.</span></span> <span data-ttu-id="6da92-109">Esse provedor pode ser usado para acessar o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] no ambiente .NET; contudo, ele pode tratar somente consultas SQL tradicionais (ou seja, consultas de bancos de dados relacionais com a exceção de consultas XML FOR XML).</span><span class="sxs-lookup"><span data-stu-id="6da92-109">This provider can be used to access [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] from the .NET environment; however, it can handle only traditional SQL queries (that is, relational database queries with the exception of FOR XML queries).</span></span> <span data-ttu-id="6da92-110">Não é possível executar modelos XML ou consultas XPath do servidor no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6da92-110">You cannot execute XML templates or the server-side XPath queries in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6da92-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="6da92-111">In This Section</span></span>  
 [<span data-ttu-id="6da92-112">Modelo do objeto de classes gerenciadas do SQLXML</span><span class="sxs-lookup"><span data-stu-id="6da92-112">SQLXML Managed Classes Object Model</span></span>](../../../database-engine/dev-guide/sqlxml-managed-classes-object-model.md)  
 <span data-ttu-id="6da92-113">Documenta classes gerenciadas SQLXML e suas propriedades e métodos.</span><span class="sxs-lookup"><span data-stu-id="6da92-113">Documents SQLXML Managed Classes and their properties and methods.</span></span>  
  
 [<span data-ttu-id="6da92-114">Usando as classes gerenciadas do SQLXML</span><span class="sxs-lookup"><span data-stu-id="6da92-114">Using the SQLXML Managed Classes</span></span>](sqlxml-4-0-net-framework-support-managed-classes.md)  
 <span data-ttu-id="6da92-115">Fornece exemplos de uso de classes gerenciadas SQLXML.</span><span class="sxs-lookup"><span data-stu-id="6da92-115">Provides examples of using SQLXML Managed Classes.</span></span>  
  
  
