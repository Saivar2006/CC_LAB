# Ex.No: 06-VM-File-Transfer

# Transfer Files from One Virtual Machine to Another

## AIM

To Find a procedure to transfer the files from one virtual machine to another virtual machine.

## ALGORITHM

Method 1 – Copy and Paste / Drag and Drop:
1. Run the virtual machine.
2. Select Devices > Drag and Drop in VirtualBox.
3. Select Host to Guest, Guest to Host, or Bidirectional.
4. For transfer in both directions, use Bidirectional.

Method 2 – USB Drive:
1. Install the VirtualBox Extension Pack.
2. Insert the USB device.
3. Open VirtualBox Preferences > Extensions.
4. Add the downloaded Extension Pack.
5. Confirm that USB is enabled under VM Settings > USB.
6. Access the USB device from the guest operating system.

Method 3 – Shared Folder:
1. Install VirtualBox Guest Additions.
2. Open Devices > Shared Folders > Shared Folders Settings.
3. Click Add Share.
4. Select the host folder.
5. Give the share a name.
6. Enable Auto-mount and Make permanent.
7. Click OK and access the shared folder from the guest OS.

## PROGRAM / CODE

```text
No program is specified in the manual. The experiment is a file-transfer procedure using VirtualBox features.
```

## SAMPLE INPUT

```text
A source file stored on the host or source virtual machine.
```

## SAMPLE OUTPUT

```text
The file becomes accessible in the destination environment through drag-and-drop, USB sharing, or a configured shared folder.
```

## RESULT

Thus the procedure to transfer the files from one virtual machine to another virtual machine is executed successfully.

---

### Files

- `README.md` – Complete experiment record
- `screenshots/` – Place your actual lab screenshots here

> **Note:** The content is organized from the supplied Cloud Computing Lab Manual. Where the manual gives a procedure rather than an algorithm or source program, that original procedure is preserved instead of inventing unrelated content.
