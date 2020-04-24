This tutorial describes the process of creating a startup executable from a VI and deploying it to run each time the LINX device starts, without the need for connection back to LabVIEW on the desktop.

1. Open the LabVIEW project created in the previous tutorial.

2. Expand the LINX target (BBB or RPI).

3. Right Build Specifications and choose New»Real-Time Application.

4. Rename the build specification.

5. Click the Source Files section on the left side of the dialog.

6. Under Project Files select the top level VI (Blink.vi in the example) and click the right arrow to add it to Startup VIs.

7. Click OK.

8. Right click the new build specification and choose Build.

9. Click Done.

10. Right click the new build specification and choose Run as Startup.

11. Click Yes to reboot the target.

12. The VI will now run whenever the target is powered on.