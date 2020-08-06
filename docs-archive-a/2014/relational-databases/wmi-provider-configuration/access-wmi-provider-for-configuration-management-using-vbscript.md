---
title: Modificar propriedades avançadas do serviço de SQL Server usando o VBScript | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- VBScript [WMI]
- modifying SQL Server Service properties
- WMI Provider for Configuration Management, VBScript
ms.assetid: f3c5d981-eaa3-4d34-9b91-37e42636aa81
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 2cf722b00a31723b77624c33fef81a82ff0cb926
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583403"
---
# <a name="modify-sql-server-service-advanced-properties-using-vbscript"></a><span data-ttu-id="cfa57-102">Modificar as propriedades avançadas do serviço do SQL Server usando o VBScript</span><span class="sxs-lookup"><span data-stu-id="cfa57-102">Modify SQL Server Service Advanced Properties using VBScript</span></span>
  <span data-ttu-id="cfa57-103">Esta seção descreve como criar um programa VBScript que lista a versão das instâncias instaladas do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que estão sendo executadas em um computador.</span><span class="sxs-lookup"><span data-stu-id="cfa57-103">This section describes how to create a VBScript program that lists the version of installed instances of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are running on a computer.</span></span>  
  
 <span data-ttu-id="cfa57-104">O exemplo de código lista as instâncias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em execução no computador e sua versão.</span><span class="sxs-lookup"><span data-stu-id="cfa57-104">The code example lists the instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the computer and its version.</span></span>  
  
### <a name="listing-name-and-version-of-installed-instances-of-sql-server"></a><span data-ttu-id="cfa57-105">Listando nome e versão de instâncias instaladas do SQL Server</span><span class="sxs-lookup"><span data-stu-id="cfa57-105">Listing name and version of installed instances of SQL Server</span></span>  
  
1.  <span data-ttu-id="cfa57-106">Abra um documento novo em um editor de textos, como o Bloco de Notas da [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfa57-106">Open a new document in a text editor, such as [!INCLUDE[msCoName](../../includes/msconame-md.md)] Notepad.</span></span> <span data-ttu-id="cfa57-107">Copie o código que segue esse procedimento e salve o arquivo com uma extensão .vbs.</span><span class="sxs-lookup"><span data-stu-id="cfa57-107">Copy the code that follows this procedure and save the file with a .vbs extension.</span></span> <span data-ttu-id="cfa57-108">Esse exemplo é chamado test.vbs.</span><span class="sxs-lookup"><span data-stu-id="cfa57-108">This example is called test.vbs.</span></span>  
  
2.  <span data-ttu-id="cfa57-109">Conecte-se a uma instância do Provedor WMI para Gerenciamento do Computador com a função de VBScript `GetObject`.</span><span class="sxs-lookup"><span data-stu-id="cfa57-109">Connect to an instance of the WMI Provider for Computer Management with the VBScript `GetObject` function.</span></span> <span data-ttu-id="cfa57-110">Este exemplo se conecta a um computador remoto denominado mpc, mas omite o nome do computador para conectar-se ao computador local: winmgmts:root\Microsoft\SqlServer\ComputerManagement.</span><span class="sxs-lookup"><span data-stu-id="cfa57-110">This example connects to a remote computer named mpc, but omit the computer name to connect to the local computer: winmgmts:root\Microsoft\SqlServer\ComputerManagement.</span></span> <span data-ttu-id="cfa57-111">Para obter mais informações sobre a função `GetObject`, consulte a referência a VBScript.</span><span class="sxs-lookup"><span data-stu-id="cfa57-111">For more information about the `GetObject` function, see the VBScript reference.</span></span>  
  
3.  <span data-ttu-id="cfa57-112">Use o método `InstancesOf` para enumerar uma lista dos serviços.</span><span class="sxs-lookup"><span data-stu-id="cfa57-112">Use the `InstancesOf` method to enumerate a list of the services.</span></span> <span data-ttu-id="cfa57-113">Os serviços também podem ser enumerados usando uma consulta de WQL simples e um método `ExecQuery`, em vez do método `InstancesOf`.</span><span class="sxs-lookup"><span data-stu-id="cfa57-113">The services can also be enumerated by using a simple WQL query and an `ExecQuery` method instead of the `InstancesOf` method.</span></span>  
  
4.  <span data-ttu-id="cfa57-114">Use o método `ExecQuery` e uma consulta WQL para recuperar o nome e a versão das instâncias instaladas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfa57-114">Use the `ExecQuery` method and a WQL query to retrieve the name and version of the installed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="cfa57-115">Salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="cfa57-115">Save the file.</span></span>  
  
6.  <span data-ttu-id="cfa57-116">Execute o script digitando `cscript test.vbs` no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="cfa57-116">Run the script by typing `cscript test.vbs` at the command prompt.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfa57-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="cfa57-117">Example</span></span>  
  
```  
set wmi = GetObject("WINMGMTS:\\.\root\Microsoft\SqlServer\ComputerManagement12")  
for each prop in wmi.ExecQuery("select * from SqlServiceAdvancedProperty where SQLServiceType = 1 AND PropertyName = 'VERSION'")  
WScript.Echo prop.ServiceName & " " & prop.PropertyName & ": " & prop.PropertyStrValue  
next  
```  
  
  
