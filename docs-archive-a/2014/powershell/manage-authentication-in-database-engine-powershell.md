---
title: Gerenciar a autenticação no PowerShell do Mecanismo de Banco de Dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: ab9212a6-6628-4f08-a38c-d3156e05ddea
author: stevestein
ms.author: sstein
ms.openlocfilehash: 018a2698a43148af971622f54c8418bf23c2c781
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679389"
---
# <a name="manage-authentication-in-database-engine-powershell"></a><span data-ttu-id="b44ef-102">Gerenciar a autenticação no Mecanismo de Banco de Dados com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="b44ef-102">Manage Authentication in Database Engine PowerShell</span></span>
  <span data-ttu-id="b44ef-103">Por padrão, os componentes do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell usam a Autenticação do Windows ao conectar a uma instância do [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b44ef-103">By default, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell components use Windows Authentication when connecting to an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="b44ef-104">Você pode usar a Autenticação do SQL Server, definindo uma unidade virtual do PowerShell ou especificando os parâmetros `-Username` e `-Password` para `Invoke-Sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="b44ef-104">You can use SQL Server Authentication by either defining a PowerShell virtual drive, or by specifying the `-Username` and `-Password` parameters for `Invoke-Sqlcmd`.</span></span>  
  
1.  <span data-ttu-id="b44ef-105">**Antes de começar:**  [Permissões](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="b44ef-105">**Before you begin:**  [Permissions](#Permissions)</span></span>  
  
2.  <span data-ttu-id="b44ef-106">**To set authentication, using:**  [A Virtual Drive](#SQLAuthVirtDrv), [Invoke-Sqlcmd](#SQLAuthInvSqlCmd)</span><span class="sxs-lookup"><span data-stu-id="b44ef-106">**To set authentication, using:**  [A Virtual Drive](#SQLAuthVirtDrv), [Invoke-Sqlcmd](#SQLAuthInvSqlCmd)</span></span>  
  
##  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b44ef-107">Permissões</span><span class="sxs-lookup"><span data-stu-id="b44ef-107">Permissions</span></span>  
 <span data-ttu-id="b44ef-108">Todas as ações que você pode executar em uma instância do [!INCLUDE[ssDE](../includes/ssde-md.md)] são controladas pelas permissões concedidas às credenciais de autenticação usadas na conexão à instância.</span><span class="sxs-lookup"><span data-stu-id="b44ef-108">All actions you can perform in an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)] are controlled by the permissions granted to the authentication credentials used to connect to the instance.</span></span> <span data-ttu-id="b44ef-109">Por padrão, o provedor do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e cmdlets usam a conta do Windows na qual ele está sendo executado para estabelecer uma conexão de Autenticação do Windows com o [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b44ef-109">By default, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider and cmdlets use the Windows account under which it is running to make a Windows Authentication connection to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="b44ef-110">Para fazer uma conexão de Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , forneça uma ID de logon e uma senha de Autenticação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b44ef-110">To make a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication connection you must supply a SQL Server Authentication login ID and password.</span></span> <span data-ttu-id="b44ef-111">Ao usar o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provedor, você deve associar as [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] credenciais de logon a uma unidade virtual e, em seguida, usar o comando Change Directory ( `cd` ) para se conectar a essa unidade.</span><span class="sxs-lookup"><span data-stu-id="b44ef-111">When using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider, you must associate the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login credentials with a virtual drive, and then use the change directory command (`cd`) to connect to that drive.</span></span> <span data-ttu-id="b44ef-112">No Windows PowerShell, credenciais de segurança só podem ser associadas a unidades virtuais.</span><span class="sxs-lookup"><span data-stu-id="b44ef-112">In Windows PowerShell, security credentials can only be associated with virtual drives.</span></span>  
  
##  <a name="sql-server-authentication-using-a-virtual-drive"></a><a name="SQLAuthVirtDrv"></a> <span data-ttu-id="b44ef-113">Autenticação do SQL Server usando uma unidade virtual</span><span class="sxs-lookup"><span data-stu-id="b44ef-113">SQL Server Authentication Using a Virtual Drive</span></span>  
 <span data-ttu-id="b44ef-114">**Para criar uma unidade virtual associada com um logon de Autenticação do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="b44ef-114">**To create a virtual drive associated with a SQL Server Authentication login**</span></span>  
  
1.  <span data-ttu-id="b44ef-115">Crie uma função que:</span><span class="sxs-lookup"><span data-stu-id="b44ef-115">Create a function that:</span></span>  
  
    1.  <span data-ttu-id="b44ef-116">Tenha parâmetros para o nome a ser atribuído à unidade virtual, a ID de logon e o caminho de provedor para associar com a unidade virtual.</span><span class="sxs-lookup"><span data-stu-id="b44ef-116">Has parameters for the name to give the virtual drive, the login ID, and the provider path to associate with the virtual drive.</span></span>  
  
    2.  <span data-ttu-id="b44ef-117">Usa `read-host` para solicitar a senha do usuário.</span><span class="sxs-lookup"><span data-stu-id="b44ef-117">Uses `read-host` to prompt the user for the password.</span></span>  
  
    3.  <span data-ttu-id="b44ef-118">Usa `new-object` para criar um objeto de credenciais.</span><span class="sxs-lookup"><span data-stu-id="b44ef-118">Uses `new-object` to create a credentials object.</span></span>  
  
    4.  <span data-ttu-id="b44ef-119">Usa `new-psdrive` para criar uma unidade virtual com as credenciais fornecidas.</span><span class="sxs-lookup"><span data-stu-id="b44ef-119">Uses `new-psdrive` to create a virtual drive with the supplied credentials.</span></span>  
  
2.  <span data-ttu-id="b44ef-120">Chame a função para criar uma unidade virtual com as credenciais fornecidas.</span><span class="sxs-lookup"><span data-stu-id="b44ef-120">Invoke the function to create a virtual drive with the supplied credentials.</span></span>  
  
### <a name="example-virtual-drive"></a><span data-ttu-id="b44ef-121">Exemplo (Unidade Virtual)</span><span class="sxs-lookup"><span data-stu-id="b44ef-121">Example (Virtual Drive)</span></span>  
 <span data-ttu-id="b44ef-122">Este exemplo cria uma função denominada **sqldrive** que você pode usar para criar uma unidade virtual que é associada ao logon de Autenticação e à instância especificados do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b44ef-122">This example creates a function named **sqldrive** that you can use to create a virtual drive that is associated with the specified [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication login and instance.</span></span>  
  
 <span data-ttu-id="b44ef-123">A função **sqldrive** solicita que você insira a senha para seu logon, mascarando a senha à medida que a digita.</span><span class="sxs-lookup"><span data-stu-id="b44ef-123">The **sqldrive** function prompts you to enter the password for your login, masking the password as you type it in.</span></span> <span data-ttu-id="b44ef-124">Em seguida, sempre que você usar o comando Change Directory ( `cd` ) para se conectar a um caminho usando o nome da unidade virtual, todas as operações serão executadas usando as [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] credenciais de logon de autenticação que você forneceu quando criou a unidade.</span><span class="sxs-lookup"><span data-stu-id="b44ef-124">Then, whenever you use the change directory command (`cd`) to connect to a path by using the virtual drive name, all operations are performed by using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication login credentials that you supplied when you created the drive.</span></span>  
  
```powershell
## Create a function that specifies the login and prompts for the password.  
  
function sqldrive  
{  
    param( [string]$name, [string]$login = "MyLogin", [string]$root = "SQLSERVER:\SQL\MyComputer\MyInstance" )  
    $pwd = Read-Host -AsSecureString -Prompt "Password"  
    $cred = New-Object System.Management.Automation.PSCredential -argumentlist $login, $pwd  
    New-PSDrive $name -PSProvider SqlServer -Root $root -Credential $cred -Scope 1  
}  
  
## Use the sqldrive function to create a SQLAuth virtual drive.  
sqldrive SQLAuth  
  
## CD to the virtual drive, which invokes the supplied authentication credentials.  
cd SQLAuth  
```  
  
##  <a name="sql-server-authentication-using-invoke-sqlcmd"></a><a name="SQLAuthInvSqlCmd"></a> <span data-ttu-id="b44ef-125">Autenticação de SQL Server usando Invoke-Sqlcmd</span><span class="sxs-lookup"><span data-stu-id="b44ef-125">SQL Server Authentication Using Invoke-Sqlcmd</span></span>  
 <span data-ttu-id="b44ef-126">**Para usar Invoke-Sqlcmd com a Autenticação do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="b44ef-126">**To use Invoke-Sqlcmd with SQL Server Authentication**</span></span>  
  
1.  <span data-ttu-id="b44ef-127">Use o parâmetro `-Username` para especificar uma ID de logon e o parâmetro `-Password` para especificar a senha associada.</span><span class="sxs-lookup"><span data-stu-id="b44ef-127">Use the `-Username` parameter to specify a login ID, and the `-Password` parameter to specify the associated password.</span></span>  
  
### <a name="example-invoke-sqlcmd"></a><span data-ttu-id="b44ef-128">Exemplo (Invoke-Sqlcmd)</span><span class="sxs-lookup"><span data-stu-id="b44ef-128">Example (Invoke-Sqlcmd)</span></span>  
 <span data-ttu-id="b44ef-129">Este exemplo usa o cmdlet do host de leitura para solicitar ao usuário uma senha e, depois, conecta usando a Autenticação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b44ef-129">This example uses the read-host cmdlet to prompt the user for a password, and then connects using SQL Server Authentication.</span></span>  
  
```powershell
## Prompt the user for their password.  
$pwd = Read-Host -AsSecureString -Prompt "Password"  
  
Invoke-Sqlcmd -Query "SELECT GETDATE() AS TimeOfQuery;" -ServerInstance "MyComputer\MyInstance" -Username "MyLogin" -Password $pwd  
```  
  
## <a name="see-also"></a><span data-ttu-id="b44ef-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b44ef-130">See Also</span></span>  
 <span data-ttu-id="b44ef-131">[SQL Server PowerShell](sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="b44ef-131">[SQL Server PowerShell](sql-server-powershell.md) </span></span>  
 <span data-ttu-id="b44ef-132">[Provedor de SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="b44ef-132">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="b44ef-133">cmdlet Invoke-Sqlcmd</span><span class="sxs-lookup"><span data-stu-id="b44ef-133">Invoke-Sqlcmd cmdlet</span></span>](../database-engine/invoke-sqlcmd-cmdlet.md)  
