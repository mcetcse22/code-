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

import java.util.Random;

class RandomThread extends Thread {
    public void run() {
        Random r = new Random();
        for (int i = 0; i < 20; i++) {
            int num = r.nextInt(100);
            if (num % 2 == 0) {
                new Even(num).start();
            } else {
                new Odd(num).start();
            }
        }
    }
}

class Even extends Thread {
    private int num;

    public Even(int num) {
        this.num = num;
    }

    public void run() {
        System.out.println("Square of " + num + " = " + num * num);
    }
}

class Odd extends Thread {
    private int num;

    public Odd(int num) {
        this.num = num;
    }

    public void run() {
        System.out.println("Cube of " + num + " = " + num * num * num);
    }
}

public class TestThread1 {
    public static void main(String[] args) {
        RandomThread randomThread = new RandomThread();
        randomThread.start();
    }
}


