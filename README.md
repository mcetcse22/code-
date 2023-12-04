class Display {
    public synchronized void print(String msg) {
        System.out.print(msg);
        try {
            Thread.sleep(1000);
        } catch (Exception e) {
            System.out.println(e.getMessage());
        }
        System.out.println("");
    }
}

class SyncThread extends Thread {
    private Display d;
    private String msg;

    public SyncThread(Display d, String msg) {
        this.d = d;
        this.msg = msg;
    }

    public void run() {
        d.print(msg);
    }
}

public class Test21 {
    public static void main(String args[]) {
        Display d = new Display();
        SyncThread syncThread1 = new SyncThread(d, "Hello");
        SyncThread syncThread2 = new SyncThread(d, "World");

        syncThread1.start();
        syncThread2.start();
    }
}
